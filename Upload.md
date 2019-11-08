# 图片上传接口

该接口是单独，不用传公共参数，按以下参数传输即可,
格式限制: jpg,jpeg,png
大小限制: 1MB以内

#### 请求地址:

http://47.56.100.242/img/index.php/picture/upload

#### POST请求
    
#### 普通的图片上传表单

#### Content-Type: multipart/form-data;

本类接口是最常用的、独立无依赖的接口集合

请求说明

**注意: 没有必要说明都进行Post 请求返回数据 json 格式字符串**


### 文件参数

| 参数  | 说明     | 备注           |
| ----- | -------- | -------------- |
| image | 文件对象 | 上传的文件对象 |

### t参数支持的值
头像：avatar

一般图片：pic

身份证：id_card

其它:other



### 请求业务参数

| 参数     | 说明              | 备注                                                         |
| -------- | ----------------- | ------------------------------------------------------------ |
| uid      | 登录用户id        |                                                              |
| sid      | 登录会话id        |                                                              |
| t        | 图片类型          | 传pic  |
| oss_type | oss第三方存储类型 | 空字符串 |
|          |                   |                                                              |



### 返回参数

```
{
    "_cost": "132616us",
    "_start": 1569580282.518221,
    "code": 0,
    "data": {
        "_entity_version": 1,
        "id": 1,
        "relative_path": "http://img.xxx.com/uploads/id_card/20190927/1031225d8de4fa91a11.jpg",
        "original_name": "153328829212.jpg",
        "save_name": "1031225d8de4fa91a11.jpg",
        "size": 29325,
        "ext": "jpg",
        "status": 1,
        "uid": 6,
        "category": "id_card",
        "md5": "b133d6173dd3e57a5f45365962944f71",
        "sha1": "53a278304e08c54ab6dd36a255cee84153bce6dc",
        "create_time": 1569580282,
        "update_time": 1569580282,
        "w": 270,
        "h": 386,
        "oss_key": "",
        "oss_type": "",
        "smaller_img": "http://img.xxx.com/uploads/id_card_small/20190927/1031225d8de4fa91a11.jpg"
    },
    "msg": "操作成功"
}
```
