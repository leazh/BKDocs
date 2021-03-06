
### 请求地址

/api/c/compapi/v2/job/get_public_script_list/



### 请求方法

GET


### 功能描述

查询公共脚本列表

### 请求参数


#### 通用参数

| 字段 | 类型 | 必选 |  描述 |
|-----------|------------|--------|------------|
| bk_app_code  |  string    | 是 | 应用 ID     |
| bk_app_secret|  string    | 是 | 安全密钥(应用 TOKEN)，可以通过 蓝鲸智云开发者中心 -&gt; 点击应用 ID -&gt; 基本信息 获取 |
| bk_token     |  string    | 否 | 当前用户登录态，bk_token 与 bk_username 必须一个有效，bk_token 可以通过 Cookie 获取 |
| bk_username  |  string    | 否 | 当前用户用户名，应用免登录态验证白名单中的应用，用此字段指定当前用户 |

#### 接口参数

| 字段       |  类型      | 必选   |  描述      |
|----------------------|------------|--------|------------|
| return_script_content  |  bool      | 否     | 是否需要返回脚本内容。true:返回脚本内容；false：不返回脚本内容。默认为 false。 |
| start                  |  int       | 否     | 默认 0 表示从第 1 条记录开始返回 |
| length                 |  int       | 否     | 分页查询-每页纪录数，默认为 20。如果传入 0 或者不传，表示不分页 |
| script_type            |  int    | 否     | 脚本类型。0：所有脚本类型，1：shell，2：bat，3：perl，4：python，5：powershell，6：sql。默认值为 0 |
| script_name            |  string    | 否     | 脚本名称，支持模糊查询 |


### 请求参数示例

```python
{
    "bk_app_code": "esb_test",
    "bk_app_secret": "xxx",
    "bk_token": "xxx",
    "start": 0,
    "length": 10,
    "return_script_content": false
}
```

### 返回结果示例

```python
{
    "result": true,
    "code": 0,
    "message": "success",
    "data": {
        "data": [
            {
                "id": 6862,
                "name": "a.sh",
                "version": "admin.20180627172306",
                "tag": "v1.0",
                "type": 1,
                "creator": "admin",
                "public": true,
                "bk_biz_id": 2,
                "create_time": "2018-06-27 17:23:06",
                "last_modify_user": "admin",
                "last_modify_time": "2018-06-27 17:23:06"
            },
            {
                "id": 36,
                "name": "build_version",
                "version": "admin.20180723154537",
                "tag": "v1.0",
                "type": 1,
                "creator": "admin",
                "public": true,
                "bk_biz_id": 2,
                "create_time": "2018-07-23 15:45:37",
                "last_modify_user": "admin",
                "last_modify_time": "2018-07-23 17:24:17"
            }
        ],
        "start": 0,
        "page_size": 10,
        "total_record_size": 2
    }
}
```

### 返回结果参数说明

#### data

| 字段      | 类型      | 描述      |
|-----------|-----------|-----------|
| id              | long       | 脚本 ID |
| name            | string    | 脚本名称 |
| version         | string    | 脚本版本号 |
| tag             | string    | 脚本版本描述 |
| type            | int       | 脚本类型 |
| creator         | string    | 脚本创建人 |
| public          | bool      | 是否公共脚本 |
| bk_biz_id       | long       | 业务 ID |
| create_time     | string    | 脚本创建时间 |
| last_modify_user| string    | 脚本最近一次修改人 |
| last_modify_time| string    | 脚本最近一次修改时间 |
| content         | string    | 脚本内容 |