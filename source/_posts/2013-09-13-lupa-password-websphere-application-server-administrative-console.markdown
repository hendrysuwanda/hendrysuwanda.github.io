---
layout: post
title: "Lupa Password WebSphere Application Server administrative console"
date: 2013-09-13 08:55
comments: true
categories: ["websphere"]
---

Di laptop gw, sudah terinstall WebSphere Application Server 8.5, tapi sudah lama nggak pakai, dan sialnya hari ini (12/09/2013) gw berkeinginan mau memakainya.

Ketika di jalanakan & ingin masuk ke Administrative console (ibm/console), s**l, gw lupa passwordnya :(

Setelah google, ternyata kita bisa non-aktifkan security mode dari websphere dengan cara.

1) Matikan dulu websphere (jika masih jalan)
2) Buka file `security.xml` yang ada fi folder `<HOME_WEBSPHERE>\AppServer\profiles\<PROFILES NAME>\config\cells\<NODE CELL NAME>`, contoh di tempat saya ada di, `C:\Program Files (x86)\IBM\WebSphere\AppServer\profiles\AppSrv01\config\cells\JPS-01122Node01Cell`

3) Lalu edit yang ada di sini

```xml
<security:Security 
	xmi:version="2.0" 
	xmlns:xmi="http://www.omg.org/XMI" 
	xmlns:orb.securityprotocol="http://www.ibm.com/websphere/appserver/schemas/5.0/orb.securityprotocol.xmi" 
	xmlns:security="http://www.ibm.com/websphere/appserver/schemas/5.0/security.xmi" 
	xmi:id="Security_1" useLocalSecurityServer="true" 
	useDomainQualifiedUserNames="false" enabled="true" cacheTimeout="600" 
	issuePermissionWarning="true" activeProtocol="BOTH" enforceJava2Security="false" 
	enforceFineGrainedJCASecurity="false" appEnabled="false" 
	dynamicallyUpdateSSLConfig="true" allowBasicAuth="true" 
	activeAuthMechanism="LTPA_1" activeUserRegistry="WIMUserRegistry_1" 
	defaultSSLSettings="SSLConfig_JPS-01122Node01_1" adminPreferredAuthMech="RSAToken_1">
```

nilai dari parameter enabled ubah dari true menjadi false,  kurang lebih jadi seperti di bawah ini.

```xml
<security:Security 
	xmi:version="2.0" 
	xmlns:xmi="http://www.omg.org/XMI" 
	xmlns:orb.securityprotocol="http://www.ibm.com/websphere/appserver/schemas/5.0/orb.securityprotocol.xmi" 
	xmlns:security="http://www.ibm.com/websphere/appserver/schemas/5.0/security.xmi" 
	xmi:id="Security_1" useLocalSecurityServer="true" 
	useDomainQualifiedUserNames="false" enabled="false" cacheTimeout="600" 
	issuePermissionWarning="true" activeProtocol="BOTH" enforceJava2Security="false" 
	enforceFineGrainedJCASecurity="false" appEnabled="false" 
	dynamicallyUpdateSSLConfig="true" allowBasicAuth="true" 
	activeAuthMechanism="LTPA_1" activeUserRegistry="WIMUserRegistry_1" 
	defaultSSLSettings="SSLConfig_JPS-01122Node01_1" adminPreferredAuthMech="RSAToken_1">
```

4) Hidupkan kembali websphere. Sekarang anda tidak perlu lagi memasukkan password untuk mengakses Administrative console (ibm/console).