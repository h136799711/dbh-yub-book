# 提现


### 1.1 提现申请


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Pay361_pay|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|shop_phone|string|是|商户号|
|shop_sub_number|string|是|商户订单号(被查询单号)|
|bank_card_number|是|所属银行|
|bank_name|是|银行名称|
|regist_bank|否|开户银行所在地区|
|regist_bank_name|否|开户银行|
|city_number|否|城市编码|
|money|是|提现金额|
|passageway_code|是|通道代码|
|card_user_name|是|持卡人姓名|
|cert_number|否|持卡人身份证号码|
|shop_sub_number|是|商户代付单号|


**返回参数** 
```
// 暂无
```

