# 银行卡、用户钱包相关

### 1.1 用户银行卡查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserBankCard_query|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|name|string|是|持有人姓名|
|user_id|integer|是|查询某一用户 0: 则全部用户|


**返回参数** 
```
{
    "data": [
        {
            "id": "6",
            "uid": "112",
            "card_no": "4012001037141112",
            "opening_bank": "Guaranty Trust Bank",
            "branch_bank": "33333",
            "name": "dachuiwang",
            "mobile": "dachuiwang"
        },
        {
            "id": "5",
            "uid": "111",
            "card_no": "622858039901128",
            "opening_bank": "First Bank",
            "branch_bank": "中国杭州分支",
            "name": "yaonana",
            "mobile": "yaonana"
        },
        {
            "id": "4",
            "uid": "108",
            "card_no": "62625262626252",
            "opening_bank": "中国银行修改",
            "branch_bank": "中国杭州分支",
            "name": "王大锤",
            "mobile": "15555555"
        },
        {
            "id": "3",
            "uid": "108",
            "card_no": "62625262626252",
            "opening_bank": "中国银行",
            "branch_bank": "中国杭州分支",
            "name": "王大锤",
            "mobile": "15555555"
        },
        {
            "id": "1",
            "uid": "108",
            "card_no": "62625262626252",
            "opening_bank": "中国银行",
            "branch_bank": "中国杭州分支",
            "name": "王大锤",
            "mobile": "15555555"
        }
    ],
    "code": 0,
    "msg": "success"
}
```




### 1.2 查询某用户钱包日志


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserWallet_queryLogHistory|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|user_id|integer|是|查询某一用户id|


**返回参数** 
```
{
    "data": {
        "count": "14",
        "list": [
            {
                "id": 70,
                "uid": "111",
                "content": "profit of fund [2]",
                "create_time": "1607128201",
                "update_time": "1607128201",
                "change_money": "0",
                "log_type": "profit_funds",
                "balance": "0",
                "frozen": "100",
                "withdraw_total": "0",
                "yuebao": "118830",
                "financial": "100"
            },
            {
                "id": 65,
                "uid": "111",
                "content": "profit yuebao",
                "create_time": "1607127001",
                "update_time": "1607127001",
                "change_money": "12",
                "log_type": "profit_bao",
                "balance": "0",
                "frozen": "100",
                "withdraw_total": "0",
                "yuebao": "118818",
                "financial": "100"
            },
            {
                "id": 55,
                "uid": "111",
                "content": "profit yuebao",
                "create_time": "1607040602",
                "update_time": "1607040602",
                "change_money": "12",
                "log_type": "profit_bao",
                "balance": "0",
                "frozen": "100",
                "withdraw_total": "0",
                "yuebao": "118806",
                "financial": "100"
            },
            {
                "id": 53,
                "uid": "111",
                "content": "deposit",
                "create_time": "1606988527",
                "update_time": "1606988527",
                "change_money": "60000",
                "log_type": "yeb_deposit",
                "balance": "0",
                "frozen": "100",
                "withdraw_total": "0",
                "yuebao": "118806",
                "financial": "100"
            },
            {
                "id": 52,
                "uid": "111",
                "content": "deposit",
                "create_time": "1606987374",
                "update_time": "1606987374",
                "change_money": "15000",
                "log_type": "yeb_deposit",
                "balance": "0",
                "frozen": "100",
                "withdraw_total": "0",
                "yuebao": "58806",
                "financial": "100"
            },
            {
                "id": 51,
                "uid": "111",
                "content": "deposit",
                "create_time": "1606987055",
                "update_time": "1606987055",
                "change_money": "6000",
                "log_type": "yeb_deposit",
                "balance": "0",
                "frozen": "100",
                "withdraw_total": "0",
                "yuebao": "43806",
                "financial": "100"
            },
            {
                "id": 50,
                "uid": "111",
                "content": "deposit",
                "create_time": "1606984106",
                "update_time": "1606984106",
                "change_money": "6000",
                "log_type": "yeb_deposit",
                "balance": "0",
                "frozen": "100",
                "withdraw_total": "0",
                "yuebao": "37806",
                "financial": "100"
            },
            {
                "id": 43,
                "uid": "111",
                "content": "profit yuebao",
                "create_time": "1606954202",
                "update_time": "1606954202",
                "change_money": "3",
                "log_type": "profit_bao",
                "balance": "0",
                "frozen": "100",
                "withdraw_total": "0",
                "yuebao": "31803",
                "financial": "100"
            },
            {
                "id": 41,
                "uid": "111",
                "content": "Freezing For withdraw",
                "create_time": "1606893841",
                "update_time": "1606893841",
                "change_money": "-100",
                "log_type": "yeb_freeze",
                "balance": "0",
                "frozen": "100",
                "withdraw_total": "0",
                "yuebao": "31803",
                "financial": "100"
            },
            {
                "id": 32,
                "uid": "111",
                "content": "commission from [202012020251530M4857A87FF6]",
                "create_time": "1606877513",
                "update_time": "1606877513",
                "change_money": "1000",
                "log_type": "commission",
                "balance": "0",
                "frozen": "0",
                "withdraw_total": "0",
                "yuebao": "30903",
                "financial": "100"
            }
        ]
    },
    "code": 0,
    "msg": "操作成功"
}
```

