# 订单查询


### 1.1 提现订单创建同时发起申请


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_WithdrawOrder_create|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|shop_phone|string|是|商户号|
|bank_card_number|string|是|所属银行|
|bank_name|string|是|银行名称|
|regist_bank|string|否|开户银行所在地区|
|regist_bank_name|string|否|开户银行|
|city_number|string|否|城市编码|
|money|string|是|提现金额,单位:元|
|passageway_code|string|是|通道代码|
|card_user_name|string|是|持卡人姓名|
|cert_number|string|否|持卡人身份证号码|

**返回参数** 
```
// 暂无
```


### 1.2 订单查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_WithdrawOrder_query|接口创建|

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
            {
                "id": 1,
                "order_no": "4630111565763147BE1BBCDC965293",  // 订单号
                "shop_phone": "13700004321", // 商户号
                "bank_card_number": "66666666", // 银行卡号
                "bank_name": "工商银行", // 银行名称
                "regist_bank": "浙江杭州xx", // 开户支行地址
                "regist_bank_name": "浙江杭州xx", // 开户支行名称
                "city_number": "xxx", // 城市编码
                "money": "10", // 金额 元
                "passageway_code": "DF00001", // 通道编码 
                "card_user_name": "王大纲",  // 姓名
                "cert_number": "33032911190011", // 身份证号码
                "notify_url": "http:\/\/47.56.100.242\/pay361\/notify", // 回调地址
                "sign": "64f17df2dc27a61f98f9100fbbc19157", // 签名
                "create_time": "1565763147", // 创建时间
                "update_time": "1565763147",
                "state": "", // 回调通知状态 成功为: success
                "pay_order_no": "", //  支付平台订单号
                "actual_money": "0.00", // 回调通知实际到账金额 
                "sub_money": "0.00", //  实际支付金额
                "service_charge": "0.00", //  手续费
                "pay_sign": "", //  回调记录的签名
                "notify_time": "0", // 回调通知实际 
                "notify_shop_phone": "" // 回调的商户号 与 shop_phone 相同 如果不同，则是异常订单
            }
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
|100|by_WithdrawOrder_info|接口创建|

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

