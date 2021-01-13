# 钱包相关


### 1.1 我的提现记录查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Withdraw_query|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|-|-|-|-|

**返回参数** 
```
{
    "data": {
        "count": "1",
        "list": [
            {
                "id": 24,
                "uid": "129",
                "account_email": "kichuak728@gmail.com",
                "name": "KRISHNAN PK",
                "account_no": "3945058150",
                "account_company": "KOTAK MAHINDRA BANK",
                "account_branch_company": "KKBK0008659",
                "create_time": "1610507244",
                "update_time": "1610507244",
                "audit_nick": "",
                "amount": "10000",
                "to_wallet_info": "{\"ifsc\":\"KKBK0008659\"}",
                "audit_status": 0
            }
        ]
    },
    "code": 0,
    "msg": "success"
}
```



### 1.2 发起提现

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Withdraw_applyByBankId|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|amount|integer|是|提现金额|
|bank_id|integer|否|银行卡id|


**返回参数** 
```
{
    "data": 5,
    "code": 0,
    "msg": "success"
}
```

