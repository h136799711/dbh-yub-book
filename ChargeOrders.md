# 订单查询


### 1.1 充值订单创建同时发起申请


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_ChargeOrder_create|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|name|string|是|姓名|
|card|string|是|充值卡号|
|evidence|string|是|图片url|
|amount|string|是|金额|
|mark|string|是|备注|

**返回参数** 
```
{
    "_cost": "1191392us",
    "_start": 1567320295.219405,
    "code": 0,
    "data": "",
    "msg": "",
    "notify_id": "666"
}
```


### 1.2 订单查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_ChargeOrder_query|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|start_time|integer|是|查询订单创建时间大于该时间，单位: 秒 |
|end_time|integer|是|查询订单创建时间小于该时间, 单位: 秒|
|min_money|integer|是|查询订单金额小于该金额, 单位: 元，不支持小数点|
|max_money|integer|是|查询订单金额小于该金额, 单位: 元，不支持小数点|


**返回参数** 
```
{
    "_cost": "451097us",
    "_start": 1565763915.703152,
    "code": 0,
    "data": {
        "count": "1",
        "list": [
        ]
    },
    "msg": "操作成功",
    "notify_id": "666"
}
```


### 1.3 订单详情


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_ChargeOrder_info|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|order_no|string|是|订单号|

**返回参数** 
```
{
    "_cost": "888862us",
    "_start": 1565763862.52181,
    "code": 0,
    "data": {
// 说明 同查询
        "id": 1,
        "order_no": "4630111565763147BE1BBCDC965293",
        "shop_phone": "13700004321",
        "bank_card_number": "66666666",
        "bank_name": "工商银行",
        "regist_bank": "浙江杭州xx",
        "regist_bank_name": "浙江杭州xx",
        "city_number": "xxx",
        "money": "10",
        "passageway_code": "DF00001",
        "card_user_name": "王大纲",
        "cert_number": "33032911190011",
        "notify_url": "http:\/\/47.56.100.242\/pay361\/notify",
        "sign": "64f17df2dc27a61f98f9100fbbc19157",
        "create_time": 1565763147,
        "update_time": 1565763147,
        "state": "",
        "pay_order_no": "",
        "actual_money": "0.00",
        "sub_money": "0.00",
        "service_charge": "0.00",
        "pay_sign": "",
        "notify_time": 0,
        "notify_shop_phone": "",
        "entity_version": 1
    },
    "msg": "操作成功",
    "notify_id": "666"
}
```

