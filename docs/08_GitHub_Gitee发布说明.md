# 08 GitHub Gitee 发布说明

## 发布前检查

- README.md 能说明项目是什么、测了什么、产出了什么
- docs 目录下测试计划、测试点分析、测试总结、简历描述已补充
- testcases/04_测试用例.md 中的用例统计和明细一致
- bugs/05_缺陷报告.md 中的缺陷/风险记录有明确复现步骤和截图路径
- evidence/screenshots 目录中保留关键执行截图
- Xmind 脑图已保存到 `assets/opencart-test-points-path-style-fixed.xmind`
- 文档中不保留工具生成提示、临时占位说明和无关截图

## Git 初始化与提交

在项目根目录执行：

```powershell
git status
git add .
git commit -m "docs: add opencart manual testing practice materials"
```

## 推送到 GitHub

1. 在 GitHub 新建仓库，建议名称：

```text
OpenCart-Manual-Testing-Practice
```

2. 添加远程地址：

```powershell
git remote add github https://github.com/你的用户名/OpenCart-Manual-Testing-Practice.git
git branch -M main
git push -u github main
```

## 推送到 Gitee

1. 在 Gitee 新建同名仓库。

2. 添加远程地址：

```powershell
git remote add gitee https://gitee.com/你的用户名/OpenCart-Manual-Testing-Practice.git
git push -u gitee main
```

## 给公司发送链接的话术

您好，这是我的 OpenCart 开源电商系统手工测试项目，主要产出包括测试计划、测试点脑图、测试用例、缺陷报告、测试总结和截图证据。项目覆盖用户注册登录、商品浏览、购物车、下单结算、后台商品管理、订单管理和客户管理等核心业务流程。

GitHub 链接：待填写

Gitee 链接：待填写

## 注意事项

- 仓库保持公开，方便企业查看
- README 中不要只写工具，要写清楚测试范围和产出
- 截图不要包含个人隐私、真实密码、真实联系方式
- 如果后续补充接口测试或自动化测试，建议单独新增目录，不要混在本次手工测试材料中
