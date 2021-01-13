# 钱包相关


### 1.1 提现记录查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Withdraw_query|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|audit_status|integer|是|0，1，-1|

**返回参数** 
```
{
    "data": {
        "count": "1",
        "list": [
            {
                "id": 24,
                "uid": "129",
                "amount": "10000",
                "create_time": "1610507244",
                "update_time": "1610507244",
                "audit_status": 0,
                "to_wallet_info": "{\"ifsc\":\"KKBK0008659\"}",
                "audit_uid": "0",
                "audit_nick": "",
                "mobile": "_1609914766830",
                "username": "test123456",
                "account_no": "3945058150",
                "name": "KRISHNAN PK",
                "account_mobile": "7904303261",
                "account_company": "KOTAK MAHINDRA BANK",
                "account_branch_company": "KKBK0008659",
                "account_email": "kichuak728@gmail.com"
            }
        ]
    },
    "code": 0,
    "msg": "success"
}
```

### 1.2 提现申请通过

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Withdraw_passYeb|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|id|integer|是|记录id|


**返回参数** 
```
{
    "data": 5,
    "code": 0,
    "msg": "success"
}
```

### 1.3 提现申请驳回

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Withdraw_denyYeb|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|id|integer|是|记录id|


**返回参数** 
```
{
    "data": 5,
    "code": 0,
    "msg": "success"
}
```


### 1.4 对提现记录发起代付

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Withdraw_createDaiPay|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|id|integer|是|提现记录id|


**返回参数** 
```
{
    "data": 5,
    "code": 0,
    "msg": "success"
}
```


