# 佣金


### 1.1 佣金统计查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_KjdsStatics_my|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|date_type|string|是|查询类型(all,today,yesterday,week,month)|

**返回参数** 
```
{
    "data": {
        "date": "today",
        "first": {
            "num": "1",
            "commission": "160",
            "order_price": 0,
            "order_commission": 0
        },
        "second": {
            "num": "0",
            "commission": 0,
            "order_price": 0,
            "order_commission": 0
        },
        "third": {
            "num": "0",
            "commission": 0,
            "order_price": 0,
            "order_commission": 0
        }
    },
    "code": 0,
    "msg": "操作成功"
}
```


