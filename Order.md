# 下单分销


### 1.1 匹配产品


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_KjdsOrder_match|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|-|-|-|-|

**返回参数** 
```
{
    "data": {
        "title": "Sony WH-1000XM4 Wireless Noise-Cancelling Over-the-Ear Headphones - Blue",
        "item_id": 3,  // 产品id
        "price": "50000", // 产品价格
        "vip_level": 1, // 用户vip等级
        "commission_per": "0.0000", // 佣金比例
        "commission_fixed": 1000 // 固定佣金金额
    },
    "code": 0,
    "msg": "操作成功"
}
```



### 1.2 下单


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_KjdsOrder_create|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|item_id|integer|是|匹配产品返回的item_id|


**返回参数** 
```
{
    "data": "202012010635070K5801C81E72", // 订单编号
    "code": 0,
    "msg": "操作成功"
}
```

### 1.3 订单查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_KjdsOrder_query|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|-|-|-|-|


**返回参数** 
```
{
    "data": [
        {
            "id": 3,
            "order_no": "202012010635070K5801C81E72",
            "price": "164000",
            "item_title": "Sony WH-1000XM3 Wireless Noise-Canceling Over-Ear Headphones Silver",
            "create_time": "1606804507",
            "update_time": "1606804507",
            "uid": "109",
            "create_day": 20201201,
            "create_month": 202012,
            "create_year": 2020,
            "user_commission": "0.000000",
            "user_level": 1,
            "username": "dbh6666",
            "item_id": 2,
            "user_commission_fixed": 1000, 
            "commission_amount": 1000 // 该订单的总佣金
        },
        {
            "id": 2,
            "order_no": "202012010629180K5199ECCBC8",
            "price": "50000",
            "item_title": "Sony WH-1000XM4 Wireless Noise-Cancelling Over-the-Ear Headphones - Blue",
            "create_time": "1606804158",
            "update_time": "1606804158",
            "uid": "109",
            "create_day": 20201201,
            "create_month": 202012,
            "create_year": 2020,
            "user_commission": "0.000000",
            "user_level": 1,
            "username": "dbh6666",
            "item_id": 3,
            "user_commission_fixed": 1000,
            "commission_amount": 1000
        }
    ],
    "code": 0,
    "msg": "操作成功"
}
```


### 1.4 实时佣金订单


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_KjdsOrder_queryCommission|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|-|-|-|-|


**返回参数** 
```
{
    "data": [
        {
            "id": 8,
            "price": "50000", 
            "item_title": "Sony WH-1000XM4 Wireless Noise-Cancelling Over-the-Ear Headphones - Blue",
            "create_time": "1606814367",
            "commission": 1000 
        }
    ],
    "code": 0,
    "msg": "操作成功"
}
```

