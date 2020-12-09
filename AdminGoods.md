# 产品

### 1.1 产品查询


**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_KjdsGoods_query|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|title|string|是|标题|

**返回参数** 
```
{
    "data": {
        "count": "5",
        "list": [
            {
                "id": 5,
                "title": "[002]WH-1000XM4 Wireless Noise-Cancelling Over-the-Ear Headphones - Blue",
                "price": "100000",
                "img_url": "https://i.ebayimg.com/images/g/xsEAAOSwC1pdjjAF/s-l500.jpg",
                "vip_level": 1,
                "status": 1
            },
            {
                "id": 4,
                "title": "[001]WH-1000XM4 Wireless Noise-Cancelling Over-the-Ear Headphones - Blue",
                "price": "60000",
                "img_url": "https://i.ebayimg.com/images/g/xsEAAOSwC1pdjjAF/s-l500.jpg",
                "vip_level": 1,
                "status": 1
            },
            {
                "id": 3,
                "title": "Sony WH-1000XM4 Wireless Noise-Cancelling Over-the-Ear Headphones - Blue",
                "price": "50000",
                "img_url": "https://i.ebayimg.com/images/g/xsEAAOSwC1pdjjAF/s-l500.jpg",
                "vip_level": 1,
                "status": 1
            },
            {
                "id": 2,
                "title": "Sony WH-1000XM3 Wireless Noise-Canceling Over-Ear Headphones Silver",
                "price": "164000",
                "img_url": "https://i.ebayimg.com/images/g/xsEAAOSwC1pdjjAF/s-l500.jpg",
                "vip_level": 2,
                "status": 1
            },
            {
                "id": 1,
                "title": "Sony WH-1000XM3 Wireless Noise-Canceling Over-Ear Headphones Silver",
                "price": "324000",
                "img_url": "https://i.ebayimg.com/images/g/xsEAAOSwC1pdjjAF/s-l500.jpg",
                "vip_level": 3,
                "status": 1
            }
        ]
    },
    "code": 0,
    "msg": "success"
}
```

### 1.2 产品创建

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_KjdsGoods_create|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|title|string|是|产品名|
|price|integer|是|价格|
|vip_level|integer|是|对应VIP级别|
|status|integer|是|1: 上架 0: 待上架|

**返回参数** 
```
{
    "data": 6,
    "code": 0,
    "msg": "操作成功"
}
```

### 1.3 产品编辑

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_KjdsGoods_edit|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|id|integer|是|产品id|
|title|string|是|产品名|
|price|integer|是|价格|
|vip_level|integer|是|对应VIP级别|
|status|integer|是|1: 上架 0: 待上架|

**返回参数** 
```
{
    "data": 6,
    "code": 0,
    "msg": "操作成功"
}
```


### 1.5 产品删除

**版本历史**

|service_version版本号|service_type服务名称|说明|
|----|---|---|
|100|by_KjdsGoods_del|接口创建|

**业务参数**

|参数 |类型|是否必须|备注|
| ---------------- | ------------------------ | ------------------------ | ------------------------ |
|id|integer|是|产品id|

**返回参数** 
```
{
    "data": 6,
    "code": 0,
    "msg": "操作成功"
}
```
