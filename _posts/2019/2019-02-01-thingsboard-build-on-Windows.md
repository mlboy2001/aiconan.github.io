---
layout: post
title: thingsboard-gateway build on Windows
category: iot
tags: [iot]
keywords: thingsboard, iot, gateway
excerpt: thingsboard-gateway build on Windows
---

Note: Please build thingsboard related modules before trying to build tb-gateway, since they are claimed as dependencies in tb-gateway, see pom.xml of tb-gateway:

![](http://www.aiconan.com/assets/images/2019/iot/tb-gateway_dependencies.png)


## Step1 - Clone code from git

Get clone link from [thingsboard gateway source](https://github.com/thingsboard/thingsboard-gateway)

The tb gateway folder would be called **WorkDir** below.

## Step2 - Build tb gateway

Navigate to WorkDir and run command(depends on maven and Java 8)

```
mvn clean install -DskipTests
```

Build success if you get stuff below:

![](http://www.aiconan.com/assets/images/2019/iot/tb-gateway_build_success.png)


## Step3 - Setup tb-gateway binary

> a. Navigate to WorkDir\target\windows\ and modify install.bat (seems the original install.bat is prepared for release archive, we need to modify it for mapping build files)

From

![](http://www.aiconan.com/assets/images/2019/iot/tb-gateway_install_bat_original.png)

To

![](http://www.aiconan.com/assets/images/2019/iot/tb-gateway_install_bat_modified.png)

> b. Navigate to WorkDir\target\windows\, Modify uninstall.bat as well

> c. Navigate to WorkDir\target\ , copy the tb-gateway-2.2.1-SNAPSHOT-boot.jar to WorkDir\target\windows\lib\ and modify the file name to tb-gateway.jar

![](http://www.aiconan.com/assets/images/2019/iot/tb-gateway_jar_file.pbg.png)
 

## Step4 - Start to use tb-gatewaty

Until now we get similar archive structure like tb-gateway release version at WorkDir\target\windows\, just start to use is according to guidance in [thingsboard installation guide](https://thingsboard.io/docs/iot-gateway/install/windows/)

Note: you can see log of tb-gateway from WorkDir\target\windows\log\

Below are screen shot from the website

![](http://www.aiconan.com/assets/images/2019/iot/tb-gateway_usage_1.png)

![](http://www.aiconan.com/assets/images/2019/iot/tb-gateway_usage_2.png)
---------------------------------------------------------------------------------------------------

A configuration file sample for gateway:(only host and token are updated)

![](http://www.aiconan.com/assets/images/2019/iot/tb-gateway_usage_3.png)

![](http://www.aiconan.com/assets/images/2019/iot/tb-gateway_usage_4.png)