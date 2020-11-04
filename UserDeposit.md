## 理财宝接口


### 1.1 基金转入

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Fund_purchase|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|fund_id|integer|是|转入基金ID|
|amount|integer|是|转入金额 单位: 分|

**返回参数** 
```
{
    "data": "",
    "code": 0,
    "msg": "操作成功"
}
```

### 1.2 基金转出

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Fund_redemption|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|fund_id|integer|是|转入基金ID|
|amount|integer|是|转入金额 单位: 分|

**返回参数** 
```
{
    "data": "",
    "code": 0,
    "msg": "操作成功"
}
```

### 1.3 定期明细(所有类型定期明细)

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Fund_query|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|fund_id|integer|是|基金id，传0则查询所有的除了余额宝的明细|
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
            "change_type": "purchase", // 购买转入
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
            "change_type": "redemption", // 赎回转出
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
            "change_type": "purchase",
            "log_date": "20201103",
            "log_time": "1604392345",
            "note": "1 days+0.01%"
        }
    ],
    "code": 0,
    "msg": "操作成功"
}
```

### 1.4 我的定期

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Fund_my|接口创建|

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

