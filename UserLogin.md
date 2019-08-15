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

### 1.1 用户名+密码 + 校验码 登录

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserLoginSession_loginByUsernameAndGoogleAuth|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|google_code|string|否|6位校验码, 谷歌令牌关闭情况下, 不传也没事, 打开情况下必须传否则登录失败|
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
        "google_auth_switch": 0, // 谷歌令牌开关 0：关闭 1：打开
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


### 1.2 谷歌令牌开关

开启后登录就会校验

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserLoginSession_googleAuth|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ------- | ---------| ------- | ------------------------ |
|switch|integer|是|1:开启 0:关闭|
|uid|string|是|用户id|
|sid|string|是|会话id|

**返回参数** 
```
{
    "_cost": "425517us",
    "_start": 1563170680.207814,
    "code": 0,
    "data": "",
    "msg": "操作成功",
    "notify_id": "666"
}
```


### 1.3 谷歌令牌密钥二维码-用于客户端绑定(切勿泄露)

开启后登录就会校验

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_GoogleAuth_qrcode|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ------- | ---------| ------- | ------------------------ |
|uid|string|是|用户id|
|sid|string|是|会话id|
|size|integer|是|返回的图片宽高|

**返回参数** 
```
{
    "_cost": "1173538us",
    "_start": 1565843969.690346,
    "code": 0,
// base64 图片
    "data": "data:image\/png;base64,iVB....",
    "msg": "操作成功",
    "notify_id": "666"
}
```


### 1.4 用户登出、注销


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
    "data": '',
    "msg": "操作成功",
    "notify_id": "666"
}
```


### 1.5 用户更新密码 ，根据旧密码
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
    "data": '',
    "msg": "操作成功",
    "notify_id": "666"
}
```
