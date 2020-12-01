# 佣金


### 1.1 佣金查询


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


