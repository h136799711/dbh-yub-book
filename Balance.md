# 余额查询


### 1.1 余额查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Pay361_orderQuery|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|shop_phone|string|是|商户号|
|shop_sub_number|string|是|商户订单号(被查询单号)|


**返回参数** 
```
// 暂无
```


### 1.2 视频查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Video_query|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|cate_id|integer|是|id|
|title|string|是|视频标题，模糊查询|
|page_index|integer|否|默认1|
|page_size|integer|否|默认10|

**返回参数** 
```
{
    "_cost": "32692us",
    "_start": 1564134444.021225,
    "code": 0,
    "data": {
        "count": "2",
        "list": [
            {
                "id": 1,
                "title": "鲨卷风",
                "description": "美国喜剧小品",
                "create_time": "1564130156",
                "update_time": "1564130485",
                "cate_id": "1",
                "uploader_id": "2",
                "upload_nick": "系统管理员",
                "show_status": 1,
                "cover": ""
            },
            {
                "id": 2,
                "title": "鲨卷风",
                "description": "美国喜剧小品2",
                "create_time": "1564130226",
                "update_time": "1564130226",
                "cate_id": "1",
                "uploader_id": "2",
                "upload_nick": "系统管理员",
                "show_status": 1,
                "cover": ""
            }
        ]
    },
    "msg": "操作成功",
    "notify_id": "666"
}
```

### 1.3 视频详情


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_Video_info|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|id|integer|是|id|

**返回参数** 
```
{
    "_cost": "46986us",
    "_start": 1564134305.763573,
    "code": 0,
    "data": {
        "title": "鲨卷风",
        "description": "美国喜剧小品",
        "update_time": 1564130485,
        "uploader": "系统管理员",
        "cover": "",
        "cate_name": "未分类",
        "cate_id": 1,
        "_group_source": {
            "线路2": [
                {
                    "id": 1,
                    "vid": "1",
                    "v_type": "video\/mp4",
                    "v_uri": "http:\/\/test.hebidu.cn\/example.mp4",
                    "come_from": "线路2",
                    "sort": "3",
                    "status": 1
                },
                {
                    "id": 3,
                    "vid": "1",
                    "v_type": "video\/mp4",
                    "v_uri": "http:\/\/test.hebidu.cn\/example.mp4",
                    "come_from": "线路2",
                    "sort": "2",
                    "status": 1
                }
            ],
            "线路1": [
                {
                    "id": 2,
                    "vid": "1",
                    "v_type": "video\/mp4",
                    "v_uri": "http:\/\/test.hebidu.cn\/example.mp4",
                    "come_from": "线路1",
                    "sort": "2",
                    "status": 1
                }
            ]
        }
    },
    "msg": "操作成功",
    "notify_id": "666"
}
```
