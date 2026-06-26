# 11 Postman 接口测试补充

## 补充目的

在页面功能测试之外，通过 Postman 验证接口请求、响应字段、业务规则和异常参数处理。接口测试可以帮助区分问题来源：是前端展示问题、接口返回问题，还是后端业务逻辑问题。

## 接口测试范围

| 模块 | 接口方向 | 测试重点 |
| --- | --- | --- |
| 登录 | 登录、退出、会话保持 | 正确账号、错误密码、空账号、Cookie/Token |
| 商品 | 商品列表、商品详情、搜索 | 商品字段、关键词过滤、空结果 |
| 购物车 | 添加、修改、删除商品 | 商品 ID、数量、库存、金额计算 |
| 订单 | 创建订单、查询订单 | 订单号、金额、商品明细、订单状态 |
| 后台 | 商品管理、订单管理 | 管理员权限、字段校验、状态变更 |

## Postman 集合规划

```text
OpenCart API Test
├── Auth
│   ├── Login Success
│   ├── Login Wrong Password
│   └── Logout
├── Product
│   ├── Search Product
│   └── Get Product Detail
├── Cart
│   ├── Add Product To Cart
│   ├── Update Product Quantity
│   └── Remove Product
└── Order
    ├── Create Order
    └── Get Order Detail
```

## 常用断言

| 断言类型 | 示例 |
| --- | --- |
| 状态码 | 返回 200、201、400、401 等符合预期的状态码 |
| 响应时间 | 响应时间小于设定阈值，例如 1000ms |
| 必要字段 | 响应体包含商品名称、价格、订单号等字段 |
| 业务规则 | 错误密码不能登录，超库存数量不能加入购物车 |
| 权限控制 | 未登录或非管理员不能访问后台接口 |

## 环境变量

| 变量名 | 用途 |
| --- | --- |
| `base_url` | 前台基础地址 |
| `admin_url` | 后台基础地址 |
| `user_email` | 普通用户邮箱 |
| `user_password` | 普通用户密码 |
| `admin_username` | 管理员用户名 |
| `admin_password` | 管理员密码 |
| `product_id` | 商品 ID |
| `order_id` | 订单 ID |

注意：真实密码、Token、Cookie 不要提交到公开仓库。

## 可以放进简历的表达

在 OpenCart 电商测试项目中，补充 Postman 接口测试设计，围绕登录、商品查询、购物车和订单接口设计请求参数、环境变量和基础断言，关注状态码、响应字段、异常参数和权限控制。

## 后续落地任务

- 通过浏览器开发者工具抓取 OpenCart 登录、商品、购物车、订单相关请求。
- 在 Postman 中建立 Collection 和 Environment。
- 为每个接口补充成功、异常参数、未登录或无权限访问用例。
- 导出 Collection，并把脱敏后的文件放到 `api-tests/`。
