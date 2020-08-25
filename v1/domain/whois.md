# 域名Whois查询

> 当前API版本：v1

查询域名Whois信息

`GET` <https://api.apipub.net/v1/domain/whois>

## 请求参数

|名称|类型|是否必选|示例值|描述|
|---|---|---|---|---|
|domain|String|是|baidu.com|域名|

## 返回示例

### 成功响应示例

```
{
    "Domain Name":"BAIDU.COM",
    "Registry Domain ID":"11181110_DOMAIN_COM-VRSN",
    "Registrar WHOIS Server":"whois.markmonitor.com",
    "Registrar":"MarkMonitor Inc.",
    "Registrar IANA ID":"292",
    "Registrar Abuse Contact Email":"abusecomplaints@markmonitor.com",
    "Registrar Abuse Contact Phone":"+1.2083895740",
    "Name Server":[
        "NS1.BAIDU.COM",
        "NS2.BAIDU.COM",
        "NS3.BAIDU.COM",
        "NS4.BAIDU.COM",
        "NS7.BAIDU.COM"
    ],
    "DNSSEC":"unsigned",
    "Last update":"2020-08-25T154646Z",
    "code":0,
    "msg":"successful"
}
```
```
{
    "Domain Name":"xinnet.cn",
    "ROID":"20030312s10001s00067198-cn",
    "Domain Status":[
        "clientDeleteProhibited",
        "clientUpdateProhibited",
        "clientTransferProhibited"
    ],
    "Registrant":"北京新网数码信息技术有限公司",
    "Registrant Contact Email":"admin@xinnet.com",
    "Sponsoring Registrar":"北京新网数码信息技术有限公司",
    "Name Server":[
        "ns11.xincache.com",
        "ns12.xincache.com"
    ],
    "DNSSEC":"unsigned"
    "code":0,
    "msg":"successful"
}
```
```
{
    "Domain Name":"QWQ.BEST",
    "Registry Domain ID":"D132397151-CNIC",
    "Registrar WHOIS Server":"whois.namesilo.com",
    "Registrar":"NameSilo, LLC",
    "Registrar IANA ID":"1479",
    "Registrant Organization":"See PrivacyGuardian.org",
    "Registrant State/Province":"AZ",
    "Registrant Country":"US",
    "Registrant Email":"Please query the RDDS service of the Registrar of Record identified in this output for information on how to contact the Registrant, Admin, or Tech contact of the queried domain name.",
    "Admin Email":"Please query the RDDS service of the Registrar of Record identified in this output for information on how to contact the Registrant, Admin, or Tech contact of the queried domain name.",
    "Tech Email":"Please query the RDDS service of the Registrar of Record identified in this output for information on how to contact the Registrant, Admin, or Tech contact of the queried domain name.",
    "Name Server":[
        "NS1.ALIDNS.COM",
        "NS2.ALIDNS.COM"
    ],
    "DNSSEC":"unsigned",
    "Billing Email":"Please query the RDDS service of the Registrar of Record identified in this output for information on how to contact the Registrant, Admin, or Tech contact of the queried domain name.",
    "Registrar Abuse Contact Email":"abuse@namesilo.com",
    "Registrar Abuse Contact Phone":"+1.4805240066",
    "Last update":"2020-08-25T155116.0Z"
    "code":0,
    "msg":"successful"
}
```

### 失败响应示例

域名未注册：
```
{
    "code":1,
    "msg":"Unregistered domain name!"
}
```
不支持的后缀：
```
{
    "code":1,
    "msg":"Unsupported domain name!"
}
```