### 请求地址

/api/c/compapi/v2/monitor/list_component_instance/

### 请求方法

GET

### 功能描述

批量筛选组件

根据指定的过滤条件和分页参数来筛选组件列表

#### 通用参数

| 字段 | 类型 | 必选 | 描述 |
|-----------|------------|--------|------------|
| bk_app_code  | string    | 是 | 应用 ID     |
| bk_app_secret| string    | 是 | 安全密钥(应用 TOKEN)，可以通过 蓝鲸智云开发者中心 -&gt; 点击应用 ID -&gt; 基本信息 获取 |
| bk_token     | string    | 否 | 当前用户登录态，bk_token 与 bk_username 必须一个有效，bk_token 可以通过 Cookie 获取 |
| bk_username  | string    | 否 | 当前用户用户名，应用免登录态验证白名单中的应用，用此字段指定当前用户 |

#### 接口参数

| 字段      | 类型   | 必选 | 描述     |
| --------- | ------ | ---- | -------- |
| id        | int    | | ID       |
| ip        | string | | 实例 IP   |
| component | string | | 组件名称 |
| bk_biz_id    | int    | | 业务 ID   |
| bk_cloud_id   | int    | | 云区域 ID |


#### 请求参数

```json
{
    "id": 2
}
```

### 返回结果

#### 字段说明

| 字段 | 类型 | 描述     |
| ---- | ---- | -------- |
| data | list | 组件列表 |

#### 结果示例

```json
{
    "code":"0",
    "_meta":{
        "count":1,
        "previous":null,
        "next":null
    },
    "result":true,
    "request_id":"c9cb1a973dc542508cf057822c8dc2c5",
    "message":"OK",
    "data":[
        {
            "update_time":"2018-11-01 13:35:55+0800",
            "update_user":"admin",
            "ip":"x.x.x.x",
            "component":"jmx",
            "create_user":"admin",
            "create_time":"2018-11-01 13:35:55+0800",
            "bk_biz_id":2,
            "bk_cloud_id":"0",
            "id":2,
            "is_deleted":false,
            "config":"NcYXc9rkryoeorg2+MPAe3iOIc1hDe4KcrIOhsvo\/YqR6on08RJ8ikeUUqmWwG+d1h7lQDxr25jJfzkvr8\/KJPhRpAc0iK\/x9+bt6tTsRKN\/zfOI6K1TOjTUeqcndTI0pwBbKGz9yP\/LvIGtgvtWGA=="
        }
    ]
}
```
