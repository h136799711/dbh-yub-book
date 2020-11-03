# 首页相关


### 1.1 首页接口


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_KjdsConfig_indexPage|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|uid|-|-|-|
|sid|-|-|-|

**返回参数** 
```
{
    "_cost": "3364014us",
    "_start": 1604048048.974816,
    "code": 0,
    "data": {
        "user_tip": { // 已登录用户提示
            "new_people": 0, // 
            "team_running": 0, // 
            "team_commission": 0 //
        },
        "grades": [ 
            {
                "id": 2,
                "title": "General",
                "day_orders": 0,
                "commission_percent": "0.0000",
                "min_amount": 0,
                "withdrawal_times": 0,
                "max_daily_income": 100,
                "note": "",
                "commission_fixed": 10,
                "rank": 0
            },
            {
                "id": 3,
                "title": "VIP 1",
                "day_orders": 26,
                "commission_percent": "0.0030",
                "min_amount": 6000,
                "withdrawal_times": 1,
                "max_daily_income": 500,
                "note": "VIP1",
                "commission_fixed": 0,
                "rank": 1
            },
            {
                "id": 4,
                "title": "VIP 2",
                "day_orders": 28,
                "commission_percent": "0.0032",
                "min_amount": 15000,
                "withdrawal_times": 2,
                "max_daily_income": 1300,
                "note": "VIP2",
                "commission_fixed": 0,
                "rank": 2
            },
            {
                "id": 5,
                "title": "VIP 3",
                "day_orders": 30,
                "commission_percent": "0.0034",
                "min_amount": 30000,
                "withdrawal_times": 2,
                "max_daily_income": 3000,
                "note": "VIP3",
                "commission_fixed": 0,
                "rank": 3
            },
            {
                "id": 6,
                "title": "VIP 4",
                "day_orders": 32,
                "commission_percent": "0.0036",
                "min_amount": 60000,
                "withdrawal_times": 3,
                "max_daily_income": 7000,
                "note": "VIP4",
                "commission_fixed": 0,
                "rank": 4
            },
            {
                "id": 7,
                "title": "VIP 5",
                "day_orders": 34,
                "commission_percent": "0.0038",
                "min_amount": 120000,
                "withdrawal_times": 4,
                "max_daily_income": 16000,
                "note": "VIP5",
                "commission_fixed": 0,
                "rank": 5
            },
            {
                "id": 8,
                "title": "VIP 6",
                "day_orders": 36,
                "commission_percent": "0.0040",
                "min_amount": 220000,
                "withdrawal_times": 5,
                "max_daily_income": 32000,
                "note": "VIP6",
                "commission_fixed": 0,
                "rank": 6
            }
        ]
    },
    "msg": "操作成功",
    "notify_id": "666"
}
```


### 1.2 手续费查询接口


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_KjdsConfig_withdrawFee|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|uid|-|-|-|
|sid|-|-|-|

**返回参数** 
```
{
    "_cost": "696590us",
    "_start": 1604372196.706345,
    "code": 0,
    "data": {
        "fee_per": "0.002",// 手续费百分比
        "fee_min": "100", // 手续费固定金额
        "withdrawals_min": "100" // 最小可提金额
    },
    "msg": "操作成功",
    "notify_id": "666"
}
```



