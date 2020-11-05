## 理财宝接口

### 1.0 余额宝信息

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_BaoFund_info|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|-|-|-|-|

**返回参数** 
```
{
    "data": {
        "title": "余额宝",
        "total": "136202.0000", // 所有存款金额 每日统计一次
        "yield": "0.0001" // 收益率 按每个用户等级
    },
    "code": 0,
    "msg": "操作成功"
}
```

### 1.1 余额宝认购

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_BaoFund_subscribe|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|amount|integer|是|转入金额 单位: 分|

**返回参数** 
```
{
    "data": "",
    "code": 0,
    "msg": "操作成功"
}
```

### 1.2 余额宝赎回

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_BaoFund_redeem|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|amount|integer|是|转入金额 单位: 分|

**返回参数** 
```
{
    "data": "",
    "code": 0,
    "msg": "操作成功"
}
```

### 1.3 余额宝明细

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_BaoFund_query|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|start_time|integer|是|起始时间|
|end_time|integer|是|截止时间|
|page_index|integer|是|1 分页|
|page_size|integer|是|10 每页数量|

**返回参数** 
```
{
    "data": [
        {
            "id": 5,
            "uid": "108",
            "fund_id": 1,
            "hold_fund_id": 2,
            "current_balance": "31190",
            "change_amount": "3",
            "change_type": "profit", // 收益
            "log_date": "20201103",
            "log_time": "1604398052",
            "note": ""
        },
        {
            "id": 3,
            "uid": "108",
            "fund_id": 1,
            "hold_fund_id": 2,
            "current_balance": "1190",
            "change_amount": "30000",
            "change_type": "subscribe", // 购买转入
            "log_date": "20201103",
            "log_time": "1604395997",
            "note": ""
        },
        {
            "id": 2,
            "uid": "108",
            "fund_id": 1,
            "hold_fund_id": 2,
            "current_balance": "1200",
            "change_amount": "-10",
            "change_type": "redeem", // 赎回转出
            "log_date": "20201103",
            "log_time": "1604392954",
            "note": "1 days+0.01%"
        },
        {
            "id": 1,
            "uid": "108",
            "fund_id": 1,
            "hold_fund_id": 2,
            "current_balance": "0",
            "change_amount": "1200",
            "change_type": "subscribe",
            "log_date": "20201103",
            "log_time": "1604392345",
            "note": "1 days+0.01%"
        }
    ],
    "code": 0,
    "msg": "操作成功"
}
```

### 1.4 我的余额宝

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_BaoFund_my|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|-|-|-|-|

**返回参数** 
```
{
    "data": {
        "confirmAmount": "45000", // 当前已确认金额
        "total_revenue": "0" // 总收益
    },
    "code": 0,
    "msg": "操作成功"
}
```

