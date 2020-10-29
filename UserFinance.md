## 用户资产接口

### 特殊参数说明

#### device_type:  

### 1.1 

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

