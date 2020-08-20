# 手机号信息查询

> 当前API版本：v1

查询手机号相关信息，**支持国际各国家手机号查询**。

可以验证手机号**是否有效**、手机号**所在国家(代码)**、手机号类型、输出各种国际标准(E164,INTERNATIONAL,National,RFC3966)号码格式、**手机号所在地区**、**服务提供商**、时区。

数据来自[Google's libphonenumber](https://github.com/google/libphonenumber)

`GET` <https://api.apipub.net/v1/phonenum/query>

## 请求参数

|名称|类型|是否必选|示例值|描述|
|---|---|---|---|---|
|phonenum|String|是|8615728115525|手机号，**需要加上国际代码，不需要加号**。|

## 返回数据

|名称|类型|示例值|描述|
|---|---|---|---|
|phonenum|String|+8615728115525|查询的手机号|
|code|Integer|0|查询状态，0:成功，1:失败|
|msg|String|successful|查询状态信息|
|is_valid|bool|true|是否为有效手机号|
|region_code|String|CN|手机号所在地区代码|
|number_type|String|MOBILE|手机号类型|
|format|Array|{"E164": "+8615728115525","INTERNATIONAL": "+86 157 2811 5525","National": "157 2811 5525","RFC3966": "tel:+86-157-2811-5525"}|国际标准(E164,INTERNATIONAL,National,RFC3966)号码格式|
|area|String|Shenzhen, Guangdong|手机号所在地区|
|area_cn|String|广东省深圳市|手机号所在地区中文结果|
|carrier|String|China Mobile|手机号服务提供商|
|carrier_cn|String|中国移动|手机号服务提供商中文结果(可能为空)|
|time_zone|Array|["Asia/Shanghai"]|手机号所在时区|

## 示例

### 成功响应示例

```
{
    "phonenum":"+8615728115525",
    "is_valid":true,
    "code":0,
    "msg":"successful",
    "region_code":"CN",
    "number_type":"MOBILE",
    "format":{
        "E164":"+8615728115525",
        "INTERNATIONAL":"+86 157 2811 5525",
        "National":"157 2811 5525",
        "RFC3966":"tel:+86-157-2811-5525"
    },
    "area":"Shenzhen, Guangdong",
    "area_cn":"广东省深圳市",
    "carrier":"China Mobile",
    "carrier_cn":"中国移动",
    "time_zone":[
        "Asia/Shanghai"
    ]
}
```
```
{
    "phonenum":"+85266585286",
    "code":0,
    "msg":"successful",
    "is_valid":true,
    "region_code":"HK",
    "number_type":"MOBILE",
    "format":{
        "E164":"+85266585286",
        "INTERNATIONAL":"+852 6658 5286",
        "National":"6658 5286",
        "RFC3966":"tel:+852-6658-5286"
    },
    "area":"Hong Kong SAR China",
    "area_cn":"中国香港特别行政区",
    "carrier":"HKT",
    "carrier_cn":"香港移动通讯",
    "time_zone":[
        "Asia/Hong_Kong"
    ]
}
```
```
{
    "phonenum":"+18166236359",
    "code":0,
    "msg":"successful",
    "is_valid":true,
    "region_code":"US",
    "number_type":"FIXED_LINE_OR_MOBILE",
    "format":{
        "E164":"+18166236359",
        "INTERNATIONAL":"+1 816-623-6359",
        "National":"(816) 623-6359",
        "RFC3966":"tel:+1-816-623-6359"
    },
    "area":"Missouri",
    "area_cn":"美国",
    "carrier":"",
    "carrier_cn":"",
    "time_zone":[
        "America/Chicago"
    ]
}
```
```
{
    "phonenum":"+447734829156",
    "code":0,
    "msg":"successful",
    "is_valid":true,
    "region_code":"GB",
    "number_type":"MOBILE",
    "format":{
        "E164":"+447734829156",
        "INTERNATIONAL":"+44 7734 829156",
        "National":"07734 829156",
        "RFC3966":"tel:+44-7734-829156"
    },
    "area":"United Kingdom",
    "area_cn":"英国",
    "carrier":"O2",
    "carrier_cn":"",
    "time_zone":[
        "Europe/Guernsey",
        "Europe/Isle_of_Man",
        "Europe/Jersey",
        "Europe/London"
    ]
}
```


### 失败响应示例

```
{
    "phonenum":"+86157281155259",
    "code":1,
    "msg":"Invalid Phone Number."
}
```