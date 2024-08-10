# wk7-nacos-sentinel
https://www.fangzhipeng.com/spring-cloud.html

Set up Spring Cloud Alibaba, integrating nacos and sentinel with Sprig Boot Admin, as followed by the Fig.1 below.

<img src="./img/nacos-sentinel1.png" alt="nacos-sentinel" width="100%">
<img src="./img/nacos-sentinel2.png" alt="nacos-sentinel" width="100%">
<p style="margin: 0;">Fig.1 Nacos-Sentinel</p>

## Nacos

**Step1**, 

```sh
cd nacos/bin
```

```sh
sh startup.sh -m standalone
```

```sh
http://localhost:8848/nacos/
```

username: nacos, password: nacos, as followed by the Fig.2 below.
<div style="text-align: center;">
    <img src="./img/nacos.png" alt="nacos" width="100%">
    <p style="margin: 0;">Fig.2 Nacos</p>
</div>

**Step2**, run NacosProviderApplication.java, NacosCustomerApplication.java, as followed by the Fig.3-4.

<div style="text-align: center;">
    <img src="./img/nacos-provider-runner.png" alt="nacos-provider-runner" width="100%">
    <p style="margin: 0;">Fig.3 Nacos-Provider</p>
</div>
<div style="text-align: center;">
    <img src="./img/nacos-consumer-runner.png" alt="nacos-consumer-runner" width="100%">
    <p style="margin: 0;">Fig.4 Nacos-Consumer</p>
</div>

**Step3**, click column "Service List", indicating the successful configuration of Nacos, as followed by the Fig.5 below.

<div style="text-align: center;">
    <img src="./img/nacos-provider-consumer.png" alt="nacos-provider-consumer" width="100%">
    <p style="margin: 0;">Fig.5 Nacos</p>
</div>

## Sentinel

首先，下载sentinel dashboard, 下载完成后，使用指令启动：

```sh
java -jar sentinel-dashboard-1.6.1.jar
```
默认启动端口为8080，可以-Dserver.port=8081的形式改变默认端口。启动成功后，在浏览器上访问localhost:8080，就可以显示Sentinel的登陆界面，登陆名为sentinel，密码为sentinel。

接着，登陆sentinel dashboard成功后，并多次访问nacos-provider的localhost:8080/hi接口，在nacos访问信息Fig.6, sentinel dashboard显示了nacos-provider的接口资源信息Fig.7, 在/hi资源处设置接口的限流功能，在“+流控”按钮点击开设置界面如下,设置阈值类型为 qps，单机阈值为2，Fig.8, 

接着，测试多次快速访问nacos-provider的接口资源http://localhost:8762/hi，可以发现偶尔出现以下的信息：“Blocked by Sentinel (flow limiting)”，正常的返回逻辑为“hi forezp”，由以上可知，接口资源/hi的限流规则起到了作用，Fig.9。最后查看限流后的nacos-provider的接口资源信息Fig.10.

<div style="text-align: center;">
    <img src="./img/sentinel-provider.png" alt="sentinel-provider" width="100%">
    <p style="margin: 0;">Fig.6 Sentinel-Provider(Page)</p>
</div>
<div style="text-align: center;">
    <img src="./img/sentinel-provider-res.png" alt="sentinel-provider-res" width="100%">
    <p style="margin: 0;">Fig.7 Sentinel-Provider(Resource)</p>
</div>
<div style="text-align: center;">
    <img src="./img/sentinel-provider-limit.png" alt="sentinel-provider-limit" width="100%">
    <p style="margin: 0;">Fig.8 Sentinel-Provider(Limit)</p>
</div>
<div style="text-align: center;">
    <img src="./img/sentinel-provider-limit-res1.png" alt="sentinel-provider-limit-res1" width="100%">
    <img src="./img/sentinel-provider-limit-res2.png" alt="sentinel-provider-limit-res2" width="100%">
    <p style="margin: 0;">Fig.9 Sentinel-Provider(Limit Result)</p>
</div>
<div style="text-align: center;">
    <img src="./img/sentinel-provider-limit-page.png" alt="sentinel-provider-limit-page" width="100%">
    <p style="margin: 0;">Fig.10 Sentinel-Provider(Renewed Page)</p>
</div>

- Sentinel Dashboard ([Download for Mac](https://github.com/alibaba/Sentinel/releases/download/1.6.1/sentinel-dashboard-1.6.1.jar))

