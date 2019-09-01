# 订单查看


### 1.1 订单查看



**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Pay361_orderInfo|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|shop_phone|string|否|商户号，不传则使用默认|
|shop_sub_number|string|是|商户订单号(被查询单号)|


**返回参数** 
```
{
    "_cost": "419890us",
    "_start": 1567321599.32515,
    "code": 0,
    "data": {
        "id": 70,
        "order_no": "8791431567320295465038A9683597",
        "shop_phone": "18912344321",
        "bank_card_number": "6236681420018999946",
        "bank_name": "建设银行",
        "regist_bank": "",
        "regist_bank_name": "",
        "city_number": "",
        "money": "100",
        "passageway_code": "DF00001",
        "card_user_name": "陈娜",
        "cert_number": "",
        "notify_url": "http://47.56.100.242/index.php/pay361/notify",
        "sign": "13154cae973fb9064f1cb564268dcbf7",
        "create_time": 1567320295,
        "update_time": 1567321408,
        "state": "1",
        "pay_order_no": "8791431567320295465038A9683597",
        "actual_money": "103.0000",
        "sub_money": "100.0000",
        "service_charge": "3.0000",
        "pay_sign": "8b7816d114d67501d2af24c32b9fce1269575a4ad093208347cc9901e15341ec",
        "notify_time": 1567321408,
        "notify_shop_phone": "18912344321",
        "entity_version": 1
    },
    "msg": "操作成功",
    "notify_id": "666"
}
```

