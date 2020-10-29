## 用户登录、注册接口


### 特殊参数说明


### 1.1 用户名 + 密码 登录

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserLoginSession_loginByUsername|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|username|string|是|用户名（登录用户名 6-24英文数字）|
|password|string|是|密码（8-24位）|

**返回参数** 
```
{
    "_cost": "3700984us",
    "_start": 1603950592.711791,
    "code": 0,
    "data": {
        "grade_id": 1, // 用户等级 默认 1 
        "idcode": "5kZZu",  // 邀请码
        "invite_uid": 0, // 上级用户id
        "id": 105,  // 用户id
        "username": "hebidu4", // 用户名
        "sid": "1W#e2bc98d1cecd7d7803ce7b9095677485" // 会话id
    },
    "msg": "success",
    "notify_id": "666"
}
```

### 1.2 用户注册


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserLoginSession_registerByUsername|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ------- | ---------| ------- | ------------------------ |
|username|string|是|用户名（登录用户名 6-24英文数字）|
|password|string|是|密码（8-24位）|
|idcode|string|是|邀请码|

**返回参数** 
```
{
    "_cost": "1669532us",
    "_start": 1603950200.167019,
    "code": 0,
    "data": 105, // 注册成功用户id
    "msg": "操作成功",
    "notify_id": "666"
}
```

### 1.3 用户登出、注销

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_LoginSession_logout|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ------- | ---------| ------- | ------------------------ |
|uid|string|是|用户id|
|sid|string|是|会话id|

**返回参数** 
```
{
    "_cost": "425517us",
    "_start": 1563170680.207814,
    "code": 0,
    "data": '',
    "msg": "操作成功",
    "notify_id": "666"
}
```

### 1.4 用户修改密码 ，根据旧密码
**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserLoginSession_updatePwdByOldPwd|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ------- | ---------| ------- | ------------------------ |
|old_pwd|string|是|旧密码|
|new_pwd|string|是|新密码|
|uid|string|是|用户id|
|sid|string|是|会话id|

**返回参数** 
```
{
    "_cost": "425517us",
    "_start": 1563170680.207814,
    "code": 0,
    "data": [],
    "msg": "操作成功",
    "notify_id": "666"
}
```
