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
    "data": "data:image\/png;base64,iVBORw0KGgoAAAANSUhEUgAAAaQAAAGkCAYAAAB+TFE1AAAACXBIWXMAAA7EAAAOxAGVKw4bAAAMkklEQVR4nO3d0W7buBZAUedi\/v+XMw8XBQap08oxJW5Saz0PYkuitDsCDv3x+fn5+QCAyf43+wsAwOMhSABECBIACYIEQIIgAZAgSAAkCBIACYIEQIIgAZAgSAAkCBIACYIEQIIgAZAgSAAkCBIACYIEQIIgAZAgSAAkCBIACYIEQIIgAZAgSAAkCBIACYIEQMI\/V3zIx8fHFR+zpM\/Pz7\/+N3c8f6PPyy7n+chxHDX6\/M363DuugxlGroHv+D8kABIECYAEQQIgQZAASBAkABIECYAEQQIgQZAASBAkABIu2akBXmVa\/ufOOHdH\/+YV0\/zsKxekHRb0zIdp+fydcV5mHe+srXRoKd9vR5XWn1d2ACQIEgAJggRAgiABkCBIACQIEgAJggRAgiABkJAbjD3C4GnLzOsxawcBOxdwlOfVcUsGiXWVdzg4+t1mfe7ov\/fKcZQfbOXvxmu8sgMgQZAASBAkABIECYAEQQIgQZAASBAkABIECYAEg7GbKf0c8TN321mhPkRbZ0eMexGkBczaQQDgSl7ZAZAgSAAkCBIACYIEQIIgAZAgSAAkCBIACYIEQILBWOCv6jsm1L8fxwjSRs7Y0eHI35y1Q8QKD5cVvuPV7DzCd7yyAyBBkABIECQAEgQJgARBAiBBkABIECQAEgQJgASDsQuYOSA467NHf255QHWXQeVXPrt8PZhnySBZzD0jr0l9Qn+n9Xen6zbLTuvlbF7ZAZAgSAAkCBIACYIEQIIgAZAgSAAkCBIACYIEQEJuMNZw3ZrqE\/ojv9\/onRXqzrgnd7nPdzmOilyQeM+MB+rMm7L+\/e7mbuuPsbyyAyBBkABIECQAEgQJgARBAiBBkABIECQAEgQJgASDsfzR6KHD+hBj\/Xjr5w\/ecUmQdtg+hT8zUd8y8p672\/17t+Mt8coOgARBAiBBkABIECQAEgQJgARBAiBBkABIECQAEpbcqWGnn8zeZQjP0GvLrOsxej3vstPFyPOywzF8Z8kg8Z6jC+uMhT9jR4eZxzuaHTGec1724JUdAAmCBECCIAGQIEgAJAgSAAmCBECCIAGQIEgAJBiMfVF9cvzo37vbDhG7HC\/P7TD0usMxvGv7IM3asmOHyfG7PcR32tFhtJFrYeb2Qrus6V2O4yuv7ABIECQAEgQJgARBAiBBkABIECQAEgQJgARBAiDh43PBCau7DajCL9Yzrxi5Xq5IxZI7NSzY0G+NfsDs8sCatcPGUeXvd8cdJ+607lc4jp\/yyg6ABEECIEGQAEgQJAASBAmABEECIEGQAEgQJAASUoOx9QHGFewyNLfLcYxWmqov2WW9jD6O1c5LKkiz3O3mfTzmHPNqN8dVZu2sMHNHh\/qOBPX7Y8YOL1fwyg6ABEECIEGQAEgQJAASBAmABEECIEGQAEgQJAASDMY+7jeA93iY+L\/CioOJ\/N+sIeSjZuzocMUaTQXJTfnczIn6kerxrVvh\/pj1HUd+7qz1sst9\/g6v7ABIECQAEgQJgARBAiBBkABIECQAEgQJgARBAiAhNRh7lAn4Nc36Kewz7DycuKL6ziPWyzFLBmkF9RDWv99IMyfgdzjP9d0X7viwP3JuVvyHu1d2ACQIEgAJggRAgiABkCBIACQIEgAJggRAgiABkHDJYOwdB9dGTo7f8fztYvS1mzHAuNP62+VYdjmOr5bdqaEyWVxTPi\/l7\/Z42BkAZvPKDoAEQQIgQZAASBAkABIECYAEQQIgQZAASBAkABKWHYzdxYwhSz\/V\/dwuA6+7HAf3c0mQ6hPwZ3y\/XX\/znnPscn3L675+v\/mHold2AEQIEgAJggRAgiABkCBIACQIEgAJggRAgiABkGCnhsc5A2m77MCwwmcfsdqA4KpGr4Ojf2\/09Z31uTOUjlWQXlSeRH\/FrAn4slkPtRXMWPejz199x5hX7BDCZ7yyAyBBkABIECQAEgQJgARBAiBBkABIECQAEgQJgIRlB2NnDa\/dbRJ9F6Vp9BXNWvd11tVYqSDdbZL6jpPodog438x1sMtOJjPc6Vi\/45UdAAmCBECCIAGQIEgAJAgSAAmCBECCIAGQIEgAJFwyGHvHQbgZQ5u7DIrWj+OM71c\/5ll2OS8jd3TY5Zw8k9qp4Qz1CzwrwLtM1O9wfevfD67ilR0ACYIEQIIgAZAgSAAkCBIACYIEQIIgAZAgSAAkbD8YW7fL1PUuxzFa\/byM\/n4GbXmHID2O30Sjdy4442E18oFwxnkZ\/dkz1M9LPYKvmLEO6uu5fG+8yys7ABIECYAEQQIgQZAASBAkABIECYAEQQIgQZAASPj4vGDKqv4TzTsNEh418rK7vvBno9fprsOxl+zUMGsnhBXc7YE643hn7qxwVHlnj50+d7RdnkMVXtkBkCBIACQIEgAJggRAgiABkCBIACQIEgAJggRAwtY\/Yb7CYF2Z83edWef6bp872tHjqP8Ue2XAd+sgvaJyQZ4pf7dfRn7HFY73qPKWMXZgaNlp3f+UV3YAJAgSAAmCBECCIAGQIEgAJAgSAAmCBECCIAGQcMlg7AqDcCMnrus\/hX2GWT87zu9WuN\/upn5Njny\/K+7JrXdqOHoC64tlFufve7vsTDHjH1jW1XXq\/4D+yis7ABIECYAEQQIgQZAASBAkABIECYAEQQIgQZAASFh2MHbWMFdpiOxs9WOd9dPfr3x2\/SfH69eY96x2fS8J0qyHwStGTzTP+HuwkzN2dJi1c8GM+3fF54tXdgAkCBIACYIEQIIgAZAgSAAkCBIACYIEQIIgAZCw7E4NdTMmpFebyv6TnY7lb+50rK+wM8V1jpyXK4Zntw\/SyJM4a3Kc793t\/NkBhKPOeF6dzSs7ABIECYAEQQIgQZAASBAkABIECYAEQQIgQZAASLhkMLY0ePXMzO9XPzdg0HZNKz5blt2pob7wR0\/Uj\/zco2Y9iGbdSLPWVH0tr8A5fE\/l\/HllB0CCIAGQIEgAJAgSAAmCBECCIAGQIEgAJAgSAAnLDsYecccdGI5+7oxBuDPOyei\/OWug+ajKAON3Zq2\/HYapZ+6IceSzr1h7uSDVb7j6AwtGO3pPWvctK143r+wASBAkABIECYAEQQIgQZAASBAkABIECYAEQQIgITcYW1caInvH6OPY5bzwuxV22JilvjNFfaOBrwTpJOWFMHqLkjMeLrO2ZDlil21v7qi8rmYpPau8sgMgQZAASBAkABIECYAEQQIgQZAASBAkABIECYAEg7EnGTlJPXqQ9RWzhv92+dxdrscudllXMz73igHarYO04m\/Kr2rWjg48N\/LhccZ9ZL3wjFd2ACQIEgAJggRAgiABkCBIACQIEgAJggRAgiABkLD1YOwdGSZs2eF67HAMrOGSIJV+s\/2Z+vc7w4xJ+Znb6OyyM0B9rfp+v5u19dfMLcd+yis7ABIECYAEQQIgQZAASBAkABIECYAEQQIgQZAASLhkMHaFgcNZZg2kzbgmMwf17rQGnef3OH\/z2DpoARb9c0fPy8wdHXbYIeKM8wzPeGUHQIIgAZAgSAAkCBIACYIEQIIgAZAgSAAkCBIACQZjN7LTYOJOxzKS88LOckGq\/Lb7O1Z4aOxwnl8x8njvdu6O2mVHkZnXd8ZOISVe2QGQIEgAJAgSAAmCBECCIAGQIEgAJAgSAAmCBEBCbjD2iJmDpzMGzc443hWGd2nY6SfbrfvfHT0nVzz7lgwS\/LLaJPq76g98eIdXdgAkCBIACYIEQIIgAZAgSAAkCBIACYIEQIIgAZBgMJal1YdA7za4S0v9\/vhKkG5q9MT\/yAfvajfRu+rRmvn96lt1zfh+Rz9zxfvIKzsAEgQJgARBAiBBkABIECQAEgQJgARBAiBBkABIMBh7U6OH5lYcwrvC0fMya\/h09HUrD\/mesUZHXl\/3kCBxEx4I3NFq694rOwASBAmABEECIEGQAEgQJAASBAmABEECIEGQAEgwGMstlIb\/nql\/v7IVzt2s77jCufmvJYNU3p7kDEeP95XFV5\/gHnmN68exwkNjl3uufj1mfb\/K9fXKDoAEQQIgQZAASBAkABIECYAEQQIgQZAASBAkABJyg7ErDAnuwHm+xp3O852OdTdHrt0Vw7O5IPFzZ+zocDcm+Zm1Mwpe2QEQIUgAJAgSAAmCBECCIAGQIEgAJAgSAAmCBEDCx6eJLQAC\/B8SAAmCBECCIAGQIEgAJAgSAAmCBECCIAGQIEgAJAgSAAmCBECCIAGQIEgAJAgSAAmCBECCIAGQIEgAJAgSAAmCBECCIAGQIEgAJAgSAAmCBECCIAGQIEgAJPwLm2f1XPLFXeAAAAAASUVORK5CYII=",
    "msg": "操作成功",
    "notify_id": "666"
}
```


### 1.3 用户登出、注销


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
