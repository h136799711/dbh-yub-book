## 用户登录接口

### 所属接口模块 base

/base

### 特殊参数说明

#### device_type:  

最大字符串长度80位   

用于标记设备的类型   

***浏览器***

可以直接使用user-agent


#### device_token   
最大80位长度
用于跟踪用户是否换了设备进行登录
这个第一次生成后就缓存到本地，下次直接使用，如果重新生成了 就有可能要重新登录，   
用某种方法实现标记某个设备(app可以生成uuid,浏览器js环境下可以使用[Valve/fingerprintjs2](https://github.com/Valve/fingerprintjs2))

### 1.1 用户名+密码登录

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserLoginSession_loginByUsername|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|username|string|是|用户名（登录用户名 6-24英文数字）|
|password|string|是|密码（8-24位）|
|device_token|string|是|登录设备标识,参考[device_token](#devicetoken)|
|device_type|string|是|登录设备类型参考[device_type](#devicetype)|

**返回参数** 
```
{
    "_cost": "3090029us",
    "_start": 1562316987.439638,
    "code": 0,
    "data": {
        "grade_id": 1, // 用户等级1
        "email": "",
        "pwd_is_set": 1, //密码是否已设置,0 表示用户还没设置 1: 已设置
        "id_validate": 0, 
        "nickname": "普通用户1562315880",
        "avatar": "",
        "idcode": "5kZZG",// 邀请码
        "invite_uid": 0,
        "id": 65, // 用户id
        "username": "hebidu3", // 用户名
        "mobile": "_1562315880791", // 手机号
        "country_no": "86", // 手机区号
        "last_login_time": 1562315880, // 上次登录时间
        "last_login_ip": "127.0.0.1",// 上次登录ip
        "mobile_auth": 0, // 手机号是否已认证
        "sid": "0S#720e1224a55a975493f92d6814b6d8e0" // 已登录用户会话ID，注意保留用于公共参数的sid
    },
    "msg": "操作成功",
    "notify_id": "666"
}
```

### 1.2 用户手机号+短信验证码登录

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|By_UserLoginSession_loginByMobileCode|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|mobile|string|是|手机号|
|country_no|string|是|国家区号86|
|device_token|string|是|登录设备标识,参考[device_token](#device_token)|
|device_type|string|是|登录设备类型参考[device_type](#device_type)|
|code|string|是|短信验证码|

**返回参数** 
```
{
    "_cost": "3090029us",
    "_start": 1562316987.439638,
    "code": 0,
    "data": {
        "grade_id": 1, // 用户等级1
        "id_validate": 0, // 是否实名认证
        "nickname": "普通用户1562315880",
        "avatar": "",
        "idcode": "5kZZG",// 邀请码
        "invite_uid": 0, // 邀请该用户注册的邀请人用户id
        "id": 65, // 用户id
        "username": "hebidu3", // 用户名
        "mobile": "_1562315880791", // 手机号
        "country_no": "86", // 手机区号
        "last_login_time": 1562315880, // 上次登录时间
        "last_login_ip": "127.0.0.1",// 上次登录ip
        "mobile_auth": 0, // 手机号是否已认证，1：已认证 0：未认证情况下 手机号不能保证是正确的手机号
        "sid": "0S#720e1224a55a975493f92d6814b6d8e0" // 已登录用户会话ID，注意保留用于公共参数的sid
    },
    "msg": "操作成功",
    "notify_id": "666"
}
```

### 1.3 用户手机号+密码+图片验证码登录

这里的验证码id请通过创建验证码图片接口来获取,
验证码是用于PC端防止频繁调用接口,防止机器破解用户密码
APP如果允许最好也要加，除非是加密过的数据

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserLoginSession_loginByMobilePassword|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|mobile|string|是|手机号|
|country_no|string|是|国家区号86|
|password|string|是|密码（8-24位）|
|device_token|string|是|登录设备标识,参考[device_token](#device_token)|
|device_type|string|是|登录设备类型参考[device_type](#device_type)|
|verify_id|string|否|验证码id|
|verify_code|string|否|用户填写的验证码|

**返回参数** 
```
{
    "_cost": "3090029us",
    "_start": 1562316987.439638,
    "code": 0,
    "data": {
        "grade_id": 1, // 用户等级1
        "id_validate": 0, 
        "nickname": "普通用户1562315880",
        "avatar": "",
        "idcode": "5kZZG",// 邀请码
        "invite_uid": 0,
        "id": 65, // 用户id
        "username": "hebidu3", // 用户名
        "mobile": "_1562315880791", // 手机号
        "country_no": "86", // 手机区号
        "last_login_time": 1562315880, // 上次登录时间
        "last_login_ip": "127.0.0.1",// 上次登录ip
        "mobile_auth": 0, // 手机号是否已认证
        "sid": "0S#720e1224a55a975493f92d6814b6d8e0" // 已登录用户会话ID，注意保留用于公共参数的sid
    },
    "msg": "操作成功",
    "notify_id": "666"
}
```

### 1.4 uid + sid 获取最新信息（可用于第三方验证用户是否已登录）

判断本地如果有缓存了uid,sid, 则通常在app打开的时候调用一次, 避免长时间不操作app时,重新获取最新信息

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserLoginSession_refresh|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ------- | ---------| ------- | ------------------------ |
|uid|string|是|用户id|
|sid|string|是|会话id|

**返回参数** 
```
{
    "_cost": "3090029us",
    "_start": 1562316987.439638,
    "code": 0,
    "data": {
        "grade_id": 1, // 用户等级1
        "id_validate": 0, 
        "nickname": "普通用户1562315880",
        "avatar": "",
        "idcode": "5kZZG",// 邀请码
        "invite_uid": 0,
        "id": 65, // 用户id
        "username": "hebidu3", // 用户名
        "mobile": "_1562315880791", // 手机号
        "country_no": "86", // 手机区号
        "last_login_time": 1562315880, // 上次登录时间
        "last_login_ip": "127.0.0.1",// 上次登录ip
        "mobile_auth": 0, // 手机号是否已认证
        "sid": "0S#720e1224a55a975493f92d6814b6d8e0" // 已登录用户会话ID，注意保留用于公共参数的sid
    },
    "msg": "操作成功",
    "notify_id": "666"
}
```

### 1.6 用户登出、注销


能主动调用就主动调用，防止sid泄露

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
    "data": [
        {
            "id": "4",
            "login_session_id": "C#7f8903dd9627d8c6e1f963c121f983d3",
            "uid": "13",
            "login_info": "\"112.16.93.124\"",
            "login_device_type": "xiaomi",
            "expire_time": "1562033761",
            "create_time": "1561428961",
            "update_time": "1561428961"
        },
        {
            "id": "6",
            "login_session_id": "C#d03013bca1de16d6f65d8e69316c5f16",
            "uid": "13",
            "login_info": "\"127.0.0.1\"",
            "login_device_type": "iphone",
            "expire_time": "1562923212",
            "create_time": "1562318412",
            "update_time": "1562318412"
        },
        {
            "id": "11",
            "login_session_id": "C#0c22c419ebe0aa682ec0001b5552b2c8",
            "uid": "13",
            "login_info": "\"112.16.93.124\"",
            "login_device_type": "xiaomi",
            "expire_time": "1560406086",
            "create_time": "1559801286",
            "update_time": "1559801286"
        }
    ],
    "msg": "操作成功",
    "notify_id": "666"
}
```
