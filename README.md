# wk7-nacos-sentinel
https://www.fangzhipeng.com/spring-cloud.html

Set up Spring Cloud Alibaba, integrating nacos and sentinel with Sprig Boot Admin, as followed by the Fig.1 below.

<img src="./img/nacos-sentinel1.png" alt="nacos-sentinel" width="100%">
<img src="./img/nacos-sentinel2.png" alt="nacos-sentinel" width="100%">
<p style="margin: 0;">Fig.1 Nacos-Sentinel</p>

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

**Step2**, 

Run NacosProviderApplication.java, NacosCustomerApplication.java, as followed by the Fig.3-4.
<img src="./img/nacos-provider-runner.png" alt="nacos-provider-runner" width="100%">
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

