---
layout: post
published: true
title: WebServices-iOS and HealthServices request.
---

<p align="justify"> This app was created as my professional practices in a Health Software and Gadgets company. The biggest problem when i was asked to develope this app was the null knowledge of the company on iOS developement. Also they had this app already in development for android devices by a bunch of peasant students. So great part of the database was only accessible throught webServices. <p> 

### TWO Weeks Work

<p align ="center"><img src="/assets/WebServicesHome.png" align="center" alt="WebServicesHome" height="600" width="340"></img></p>

<p align ="center"> The 3 main frameworks to make possible webService comunications were:</p>

<p align ="center"><img src="/assets/WebServicesASIHTTP.png" align="center" alt="AsiHTTP" height="400" width="640"></img></p>

1. [ASIHTTPRequest](http://allseeing-i.com/ASIHTTPRequest/).
2. [GitHub user: Stig,  Json Framework](https://github.com/stig/json-framework/).
3. [CFNetwork.framework](https://developer.apple.com/library/ios/documentation/CFNetwork/Reference/CFNetwork_Framework/_index.html)
4. [SystemConfiguration.frameworkMobileCoreServices.framework libz.1.2.3.dylib.](https://developer.apple.com/library/mac/documentation/networking/Reference/SysConfig/_index.html)

> These frameworks helped with the parsing of XML received data and then the handeling for cell dynamic population.

<p align ="center">
    Dynamic table populations is created througth parsing of the xml and tested with an specific id from heach user. This id is handeled directly by the server so there is no need of using iOS KeychainAcces.
</p>

<p align ="center"><img src="/assets/WebServicestablas.png" align="center" alt="Dynamic Table" height="600" width="340"></img></p>

<p align ="center"> 
    Debugging throught console was nedded since the server responses were not sended in any specific format.
</p>

<p align ="center"><img src="/assets/WebServicesDebuggin.png" align="center" alt="WebServices Debuggin" height="300" width="340"></img></p>

