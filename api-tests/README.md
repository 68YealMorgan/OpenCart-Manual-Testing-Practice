# Postman 接口测试补充

本目录用于存放 OpenCart 项目的 Postman 接口测试材料。当前阶段先整理接口测试范围、请求设计、断言思路和集合规划；后续导出的 Postman Collection、Environment 或执行报告可以继续放在本目录下。

## 建议目录

```text
api-tests/
├── README.md
├── OpenCart.postman_collection.json
├── OpenCart.local.postman_environment.json
└── reports/
```

## 接口测试范围

| 模块 | 重点接口方向 | 断言重点 |
| --- | --- | --- |
| 登录/鉴权 | 登录、退出、会话保持 | 状态码、响应提示、Cookie/Token、错误账号处理 |
| 商品查询 | 商品列表、商品详情、搜索 | 状态码、商品字段、空结果、关键词过滤 |
| 购物车 | 添加商品、修改数量、删除商品 | 商品数量、价格、库存限制、错误参数 |
| 订单 | 创建订单、查询订单、订单状态 | 订单号、金额、商品明细、状态流转 |
| 后台管理 | 商品新增/编辑、订单查询 | 权限控制、字段校验、数据一致性 |

## Postman 断言示例

```javascript
pm.test("状态码为 200", function () {
  pm.response.to.have.status(200);
});

pm.test("响应时间小于 1000ms", function () {
  pm.expect(pm.response.responseTime).to.be.below(1000);
});

pm.test("响应体包含预期字段", function () {
  const jsonData = pm.response.json();
  pm.expect(jsonData).to.have.property("success");
});
```

## 环境变量规划

| 变量名 | 说明 |
| --- | --- |
| `base_url` | OpenCart 前台或接口基础地址 |
| `admin_url` | OpenCart 后台地址 |
| `user_email` | 普通用户邮箱，避免写真实密码 |
| `user_password` | 普通用户密码，建议只放本地环境变量 |
| `admin_username` | 后台管理员用户名 |
| `admin_password` | 后台管理员密码，建议只放本地环境变量 |
| `product_id` | 测试商品 ID |
| `order_id` | 测试订单 ID |

## 执行记录建议

- 每次执行前记录环境、账号、接口地址和测试数据。
- 每个接口至少覆盖成功、必填缺失、非法参数、权限不足等情况。
- 如果接口依赖登录态，先在 Postman 中保存 Cookie 或 Token。
- 导出 Collection 和 Environment 时，不提交真实密码、Token 或个人账号敏感信息。

## 面试讲解口径

可以说明：本项目在手工测试基础上补充接口测试，重点验证前后端交互和核心业务数据是否正确。Postman 用于组织请求、管理环境变量和编写基础断言，接口测试结果可以反向支持页面问题定位，例如区分是前端展示问题、接口返回问题，还是后端业务规则问题。
