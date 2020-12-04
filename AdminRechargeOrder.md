# 充值订单


### 1.1 充值订单查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_RechargeOrder_query|接口创建|

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
               "id": 38,
               "amount": 6000,
               "create_time": "1606983800",
               "update_time": "1606983800",
               "method": "pay_um",
               "uid": "111",
               "recharge_status": "wait",
               "note": ""
           },
           {
               "id": 37,
               "amount": 6000,
               "create_time": "1606983577",
               "update_time": "1606983577",
               "method": "pay_um",
               "uid": "111",
               "recharge_status": "wait",
               "note": ""
           },
           {
               "id": 36,
               "amount": 6000,
               "create_time": "1606983548",
               "update_time": "1606983548",
               "method": "pay_um",
               "uid": "111",
               "recharge_status": "wait",
               "note": ""
           },
           {
               "id": 35,
               "amount": 6000,
               "create_time": "1606983516",
               "update_time": "1606983516",
               "method": "pay_um",
               "uid": "111",
               "recharge_status": "wait",
               "note": ""
           },
           {
               "id": 33,
               "amount": 1300000,
               "create_time": "1606968115",
               "update_time": "1606968115",
               "method": "pay_um",
               "uid": "109",
               "recharge_status": "wait",
               "note": ""
           },
           {
               "id": 32,
               "amount": 1300000,
               "create_time": "1606967300",
               "update_time": "1606967300",
               "method": "pay_um",
               "uid": "109",
               "recharge_status": "wait",
               "note": ""
           },
           {
               "id": 31,
               "amount": 1300000,
               "create_time": "1606967158",
               "update_time": "1606967158",
               "method": "pay_um",
               "uid": "109",
               "recharge_status": "wait",
               "note": ""
           },
           {
               "id": 30,
               "amount": 1300000,
               "create_time": "1606966219",
               "update_time": "1606966219",
               "method": "pay_um",
               "uid": "109",
               "recharge_status": "wait",
               "note": ""
           },
           {
               "id": 29,
               "amount": 1300000,
               "create_time": "1606966173",
               "update_time": "1606966173",
               "method": "pay_um",
               "uid": "109",
               "recharge_status": "wait",
               "note": ""
           },
           {
               "id": 28,
               "amount": 1300000,
               "create_time": "1606963539",
               "update_time": "1606963539",
               "method": "pay_um",
               "uid": "109",
               "recharge_status": "wait",
               "note": ""
           }
       ],
       "code": 0,
       "msg": "操作成功"
   }
```



### 1.2 充值订单的支付信息查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_RechargeOrder_payInfo|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|id|integer|是|充值订单id|


**返回参数** 
```
{
    "data": [
        {
            "trade_no": "46008ojqOAG",// 第三方支付交易编号
            "trade_status": "WAITING_PAY", // 第三方支付状态 
            "note": "",
            "subject": "Recharge 13000.00",
            "id": "31",
            "pay_status": 0, // 支付状态 0 待支付 1 已支付
            "out_order_no": "32",  // 商品订单id
            "out_order_type": "recharge", // 商品订单类型 目前只有recharge充值订单
            "pay_code": "5096651606967300B5A84A5F336476", // 支付订单编号
            "money": "1300000",
            "pay_time": "0",// 支付时间
            "pay_type": "pay_um",// 支付方式
            "create_time": "1606967300",
            "update_time": "1606967311"
        }
    ],
    "code": 0,
    "msg": "操作成功"
}
```
