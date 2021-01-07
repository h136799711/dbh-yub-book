# 用户邀请关系


### 1.1 查询某一用户的下一级用户列表


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserInvite_queryByUserId|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|user_id|integer|是|查询的用户id|

**返回参数** 
```
{
    "data": {
        "list": [
            {
                "nickname": "普通用户1607494419",
                "head": "",
                "idcode": "0MIBK3",
                "invite_uid": "111",
                "invite_uid2": "0",
                "invite_uid3": "0"
            },
            {
                "nickname": "普通用户1607503408",
                "head": "",
                "idcode": "0MIBKA",
                "invite_uid": "111",
                "invite_uid2": "0",
                "invite_uid3": "0"
            },
            {
                "nickname": "普通用户1609916568",
                "head": "",
                "idcode": "0MIBKD",
                "invite_uid": "111",
                "invite_uid2": "0",
                "invite_uid3": "0"
            }
        ],
        "count": "3"
    },
    "code": 0,
    "msg": "操作成功"
}
```
