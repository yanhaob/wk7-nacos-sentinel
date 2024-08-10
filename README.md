# wk7-nacos-sentinel
https://www.fangzhipeng.com/spring-cloud.html
Set up Spring Cloud Alibaba, integrating nacos and sentinel with Sprig Boot Admin, as followed by the Fig.1 below.

<img src="./img/nacos-sentinel1.png" alt="nacos-sentinel" width="100%">
<img src="./img/nacos-sentinel2.png" alt="nacos-sentinel" width="100%">
<p style="margin: 0;">Fig.1 Nacos-Sentinel</p>

首先，cd nacos/bin运行指令sh startup.sh -m standalone，登陆页面http://localhost:8848/nacos/，登陆用户nacos，登陆密码为nacos。
<img src="./img/nacos.png" alt="nacos" width="100%">
<p style="margin: 0;">Fig.2 Nacos</p>

其次，run NacosProviderApplication.java, NacosCustomerApplication.java
<img src="./img/nacos-provider-runner.png" alt="nacos-provider-runner" width="100%">
<p style="text-align: center;">Fig.3 Nacos-Provider</p>
<img src="./img/nacos-consumer-runner.png" alt="nacos-consumer-runner" width="100%">
<p style="text-align: center;">Fig.4 Nacos-Consumer</p>

接着，在服务列表中查看服务，表明Nacos部署成功。
<img src="./img/nacos-provider-consumer.png" alt="nacos-provider-consumer" width="100%">
<p style="text-align: center;">Fig.5 Nacos</p>


