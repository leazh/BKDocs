
### 请求地址

/api/c/compapi/v2/monitor_v3/delete_alarm_strategy/



### 请求方法

POST


### 功能描述

删除告警策略

### 请求参数


#### 通用参数

| 字段 | 类型 | 必选 |  描述 |
|-----------|------------|--------|------------|
| bk_app_code  |  string    | 是 | 应用 ID     |
| bk_app_secret|  string    | 是 | 安全密钥(应用 TOKEN)，可以通过 蓝鲸智云开发者中心 -&gt; 点击应用 ID -&gt; 基本信息 获取 |
| bk_token     |  string    | 否 | 当前用户登录态，bk_token 与 bk_username 必须一个有效，bk_token 可以通过 Cookie 获取 |
| bk_username  |  string    | 否 | 当前用户用户名，应用免登录态验证白名单中的应用，用此字段指定当前用户 |

#### 接口参数

| 字段      | 类型 | 必选 | 描述       |
| :-------- | ---- | ---- | ---------- |
| bk_biz_id | int  | 是   | 业务 ID     |
| id        | int  | 是   | 告警策略 ID |

#### 示例数据

```json
{
  "bk_biz_id": 2,
  "id": 1
}
```

### 响应参数

```json
{
  "message": "OK",
  "code": "0",
  "data": null,
  "result": true
}
```