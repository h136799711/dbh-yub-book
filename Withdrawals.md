# 钱包相关


### 1.1 提现记录查询


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
        "count": "5",
        "list": [
            {
                "id": 5,
                "uid": "108",
                "create_time": "1606878476",
                "update_time": "1606878476",
                "audit_nick": "",
                "amount": "100",
                "to_wallet_info":"{\"card_no\":\"62625262626252\",\"bank_name\":\"\中\国\银\行\",\"name\":\"\王\大\锤\",\"branch_name\":\"\中\国\杭\州\分\支\"}",
                "audit_status": 0
            },
            {
                "id": 4,
                "uid": "108",
                "create_time": "1604370879",
                "update_time": "1604370891",
                "audit_nick": "网1",
                "amount": "150",
                "to_wallet_info":"{\"card_no\":\"62625262626252\",\"bank_name\":\"\中\国\银\行\",\"name\":\"\王\大\锤\",\"branch_name\":\"\中\国\杭\州\分\支\"}",
                "audit_status": 1
            },
            {
                "id": 3,
                "uid": "108",
                "create_time": "1604370863",
                "update_time": "1604370873",
                "audit_nick": "网1",
                "amount": "100",
                "to_wallet_info":"{\"card_no\":\"62625262626252\",\"bank_name\":\"\中\国\银\行\",\"name\":\"\王\大\锤\",\"branch_name\":\"\中\国\杭\州\分\支\"}",
                "audit_status": -1
            },
            {
                "id": 2,
                "uid": "108",
                "create_time": "1604370721",
                "update_time": "1604370731",
                "audit_nick": "网1",
                "amount": "100",
                "to_wallet_info":"{\"card_no\":\"62625262626252\",\"bank_name\":\"\中\国\银\行\",\"name\":\"\王\大\锤\",\"branch_name\":\"\中\国\杭\州\分\支\"}",
                "audit_status": -1
            },
            {
                "id": 1,
                "uid": "108",
                "create_time": "1604370118",
                "update_time": "1604370313",
                "audit_nick": "网1",
                "amount": "100",
                "to_wallet_info":"{\"card_no\":\"62625262626252\",\"bank_name\":\"\中\国\银\行\",\"name\":\"\王\大\锤\",\"branch_name\":\"\中\国\杭\州\分\支\"}",
                "audit_status": 1
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

