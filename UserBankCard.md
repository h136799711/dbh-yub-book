# 银行卡相关


### 1.1 用户银行卡添加


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserBankCard_bind|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|mobile|string|是|银行卡手机号|
|name|string|是|银行卡姓名|
|card_no|string|是|银行卡号|
|opening_bank|string|是|银行名|
|ifsc_code|string|是|银行ifsc编码|
|email|string|是|银行绑定邮箱|

**返回参数** 
```
{
    "code": 0,
    "data": "",
    "msg": "操作成功",
    
}
```


### 1.2 用户银行卡编辑


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserBankCard_update|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|id|integer|是|卡id|
|mobile|string|是|联系号码|
|name|string|是|姓名|
|card_no|string|是|银行卡号|
|opening_bank|string|是|银行名|
|ifsc_code|string|是|银行ifsc编码|
|email|string|是|银行绑定邮箱|

**返回参数** 
```
{
    "code": 0,
    "data": "",
    "msg": "操作成功",
    
}
```


### 1.3 用户银行卡查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserBankCard_query|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|-|-|-|-|


**返回参数** 
```
{
   "data": [
       {
           "id": "12",
           "uid": "129",
           "email": "kichuak728@gmail.com",
           "card_no": "3945058150",
           "opening_bank": "KOTAK MAHINDRA BANK",
           "branch_bank": "KKBK0008659",
           "name": "KRISHNAN PK",
           "mobile": "7904303261",
           "ifsc_code": "KKBK0008659"
       }
   ],
   "code": 0,
   "msg": "success"
}
```

### 1.4 用户银行卡取绑


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_UserBankCard_unbind|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|id|integer|是|卡id|

**返回参数** 
```
{
    "code": 0,
    "data": "success",
    "msg": "操作成功",
    
}
```
