# 支付相关


### 1.1 可用支付方式


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_KjdsConfig_paymentMethod|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|-|-|-|-|

**返回参数** 
```
{
   "code": 0,
   "data": [
       {
           "code": "fake",   // 唯一支付编号,用于后续
           "title": "模拟支付通道",
           "desc": "仅用于开发测试用"
       }
   ],
   "msg": "操作成功",
   
}
```



### 1.2 创建充值订单

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_RechargeOrder_create|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|amount|integer|是|单位:分|
|method|string|是|支付方式,1.1的code参数值|
|return_url|string|是|支付成功后跳转的页面需要绝对地址http开头且要进行url编码|


**返回参数** 
```
{
    "code": 0,
    // 返回的url编码过的付款链接
    "data": "http%3A%2F%2Fkjds.h.itboye.com%2Ffakepay%2Fjg1wOhQM6TZKopgnuRDOULqNVvTNnOBqtWh7cZuX%25252FnqQaFnu56AA9Ocv2r3NdbpG%25252FnX7zKMPeq0hYRublggyqVFsl1auw7YSrwkMbPaFbbBaZ7mYDnciSQ%25253D%25253D",
    "msg": "操作成功",
    
}
```


### 1.3 充值订单查询

**枚举类型**

recharge_status

wait 待支付
fail 失败
success 成功


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_RechargeOrder_query|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|start_time|integer|是|起时间戳 单位:秒|
|end_time|integer|是|截止时间戳 单位:秒|


**返回参数** 
```
{
    "code": 0,
    "data": [
        {
            "id": 6,
            "amount": 300,
            "create_time": "1604045939",
            "update_time": "1604045939",
            "method": "fake",
            "uid": "108",
            "recharge_status": "wait", 
            "note": ""
        },
         {
             "id": 5,
             "amount": 300,
             "create_time": "1604037678",
             "update_time": "1604037698",
             "method": "fake",
             "uid": "108",
             "recharge_status": "success", // 支付成功
             "note": ""
         },
          {
              "id": 4,
              "amount": 300,
              "create_time": "1604037678",
              "update_time": "1604037698",
              "method": "fake",
              "uid": "108",
              "recharge_status": "fail", // 支付失败
              "note": ""
          }
    ],
    "msg": "操作成功",
    
}
```
