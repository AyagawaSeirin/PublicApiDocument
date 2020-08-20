# IP信息查询

> 当前API版本：v1

查询IP地址相关信息，**支持查询IPv6地址**。

最多可查询到大洲(代码)、国家(代码)、省份(代码)、城市、运营商、组织全称、AS号、时区、经纬度、详细地区。

数据来自**GeoIP库**以及**纯真IP库**。

`GET` <https://api.apipub.net/v1/ip/query>

## 请求参数

|名称|类型|是否必选|示例值|描述|
|---|---|---|---|---|
|ip|String|是|128.101.101.101|IP地址，IPv4或IPv6均支持|

## 返回数据


|名称|类型|示例值|描述|
|---|---|---|---|
|ip|String|128.101.101.101|查询的IP地址|
|code|Integer|0|查询状态，0:成功，1:失败|
|msg|String|successful|查询状态信息|
|type|String|ipv4|IP类型|
|continent|String|北美洲|IP所在大洲|
|continent_code|String|NA|IP所在大洲的代码|
|country|String|美国|IP所在国家|
|country_iso|String|US|IP所在国家的ISO代码|
|province|String|明尼苏达州|IP所在行政区(如省级或州级)|
|province_iso|String|MN|IP所在行政区的ISO代码|
|city|String|圣保罗|IP所在城市|
|isp|String|UMN-SYSTEM|服务提供商|
|autonomous_system_organization|String|UMN-SYSTEM|服务提供商全称|
|asn|Integer|217|AS号|
|time_zone|String|America/Chicago|时区|
|latitude|Float|44.9825|经度|
|longitude|Float|-93.1863|纬度|
|area|String|美国明尼苏达大学|IP所在详细区域|

## 示例

### 成功响应示例

```
{
    "ip":"103.195.6.35",
    "code":0,
    "msg":"successful",
    "type":"ipv4",
    "continent":"亚洲",
    "continent_code":"AS",
    "country":"中国香港",
    "country_iso":"HK",
    "province":"Central and Western District",
    "province_iso":"HCW",
    "city":"Central",
    "isp":"Kamatera, Inc.",
    "autonomous_system_organization":"Kamatera, Inc.",
    "asn":64022,
    "time_zone":"Asia/Hong_Kong",
    "latitude":22.2795,
    "longitude":114.146,
    "area":"亚太地区"
}
```
```
{
    "ip":"113.116.23.15",
    "code":0,
    "msg":"successful",
    "type":"ipv4",
    "continent":"亚洲",
    "continent_code":"AS",
    "country":"中国",
    "country_iso":"CN",
    "province":"广东",
    "province_iso":"GD",
    "city":"深圳市",
    "isp":"中国电信",
    "autonomous_system_organization":"Chinanet",
    "asn":4134,
    "time_zone":"Asia/Shanghai",
    "latitude":22.5333,
    "longitude":114.1333,
    "area":"中国广东深圳市电信"
}
```
查询IPv6示例：
```
{
    "ip":"2400:3200:baba::1",
    "code":0,
    "msg":"successful",
    "type":"ipv6",
    "continent":"亚洲",
    "continent_code":"AS",
    "country":"中国",
    "country_iso":"CN",
    "province":null,
    "province_iso":null,
    "city":null,
    "isp":"阿里云",
    "autonomous_system_organization":"Hangzhou Alibaba Advertising Co.,Ltd.",
    "asn":37963,
    "time_zone":"Asia/Shanghai",
    "latitude":35,
    "longitude":105
}
```

### 失败响应示例

```
{
    "ip":"113.116.23.1555",
    "code":1,
    "msg":"Invalid IPv4 or IPv6."
}
```