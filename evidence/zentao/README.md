# 禅道缺陷记录

本目录用于保存禅道中的缺陷记录材料。当前文件基于项目中已记录的 5 个缺陷/风险点，按禅道常见字段整理，方便和禅道页面中的记录对应。

说明：这里不是禅道系统导出的原始文件，也不是禅道页面截图。等后续录入完成后，可以把缺陷列表截图、典型 BUG 详情页截图放到本目录。

## 缺陷记录汇总

| 禅道编号 | 项目编号 | 缺陷标题 | 所属模块 | 严重程度 | 优先级 | 当前状态 | 对应报告 | 截图证据 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 待录入 | BUG_001 | MacBook 商品结算时无可选支付方式 | 下单结算 | 一般 | P2 | 新建 | `bugs/05_缺陷报告.md` | `evidence/screenshots/BUG_001_checkout_payment_method_missing.png` |
| 待录入 | BUG_002 | 订单提交后邮件警告导致前端出现 JSON 解析错误弹窗 | 下单结算 | 一般 | P2 | 新建 | `bugs/05_缺陷报告.md` | `evidence/screenshots/BUG_002_order_submit_mail_json_error.png` |
| 待录入 | BUG_003 | 购物车商品数量输入负数后购物车被清空且无明确提示 | 购物车 | 一般 | P2 | 新建 | `bugs/05_缺陷报告.md` | `evidence/screenshots/BUG_003_cart_negative_quantity.png` |
| 待录入 | RISK_004 | 后台提示 install 安装目录仍存在 | 后台安全配置 | 建议 | P3 | 新建 | `bugs/05_缺陷报告.md` | `evidence/screenshots/RISK_004_install_folder_security_warning.png` |
| 待录入 | RISK_005 | storage 目录位于 Web 目录内存在潜在安全风险 | 后台安全配置 | 建议 | P3 | 新建 | `bugs/05_缺陷报告.md` | `evidence/screenshots/RISK_005_storage_directory_security_notice.png` |

## 建议录入字段

录入禅道时，建议保持字段和 `bugs/05_缺陷报告.md` 一致：

- 标题：使用缺陷报告中的缺陷标题。
- 所属模块：下单结算、购物车、后台安全配置等。
- 严重程度：一般或建议。
- 优先级：P2 或 P3。
- 复现步骤：复制缺陷报告中的复现步骤。
- 实际结果：复制缺陷报告中的实际结果。
- 预期结果：复制缺陷报告中的预期结果。
- 附件：上传 `evidence/screenshots/` 中对应截图。

## 后续截图命名

如果后续补充禅道截图，建议使用下面的命名方式：

```text
evidence/zentao/zentao_bug_list.png
evidence/zentao/zentao_bug_001_detail.png
evidence/zentao/zentao_bug_002_detail.png
```

这样仓库里会同时保留 Markdown 缺陷报告、执行截图和禅道记录截图，面试时更容易说明缺陷从发现到记录的过程。
