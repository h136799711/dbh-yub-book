# 刷单


### 1.1 刷单查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_KjdsOrder_query|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|status|string|是|all,success,fail,wait|
|username|string|是|用户名|

**返回参数** 
```

{
    "data": [
        {
            "id": 12,
            "order_no": "202012040233020N5172ECCBC8",
            "username": "dachui3",// 刷单用户名
            "user_level": 1, // 刷单时用户的VIP级别
            "commission_amount": 1000, // 刷单用户的佣金
            "parent_user": "108", // 刷单用户的上级
            "pp_user": "80", // 刷单用户的上上级
            "ppp_user": "2", // 刷单用户的上上上级
            "p_user_commission": 160,// 刷单用户的上级佣金
            "pp_user_commission": 100,// 刷单用户的上上级佣金
            "ppp_user_commission": 40 // 刷单用户的上上上级佣金
            "price": "50000", // 刷单金额
            "item_id": 3,// 刷单商品id
            // 刷单商品名称
            "item_title": "Sony WH-1000XM4 Wireless Noise-Cancelling Over-the-Ear Headphones - Blue",
            "create_time": "1607049182"
        },
        {
            "id": 11,
            "username": "dbh6666",
            "user_level": 1,
            "item_id": 3,
            "commission_amount": 1000,
            "p_user_commission": 160,
            "pp_user_commission": 100,
            "ppp_user_commission": 40,
            "parent_user": "108",
            "pp_user": "80",
            "ppp_user": "2",
            "order_no": "202012020610320K1998ECCBC8",
            "price": "50000",
            "item_title": "Sony WH-1000XM4 Wireless Noise-Cancelling Over-the-Ear Headphones - Blue",
            "create_time": "1606889432"
        },
        {
            "id": 10,
            "username": "yaonana",
            "user_level": 1,
            "item_id": 4,
            "commission_amount": 1000,
            "p_user_commission": 0,
            "pp_user_commission": 0,
            "ppp_user_commission": 0,
            "parent_user": "0",
            "pp_user": "0",
            "ppp_user": "0",
            "order_no": "202012020251530M4857A87FF6",
            "price": "60000",
            "item_title": "[001]WH-1000XM4 Wireless Noise-Cancelling Over-the-Ear Headphones - Blue",
            "create_time": "1606877513"
        }
    ],
    "code": 0,
    "msg": "操作成功"
}
```
