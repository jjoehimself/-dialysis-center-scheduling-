# Security Policy / 安全政策

> [中文] 本项目涉及医疗排班场景，公开交流中请勿包含真实患者或医护隐私数据。  
> [English] This project involves healthcare scheduling workflows. Do not include real patient or staff private data in public communication.

## 不要公开真实患者数据 / Do Not Share Real Patient Data Publicly

**[中文]**  
请不要在 GitHub issue、pull request、截图、演示 JSON、讨论区或公开错误报告中包含真实患者资料。

**[English]**  
Please do not include real patient information in GitHub issues, pull requests, screenshots, demo JSON files, discussions, or public bug reports.

**[中文]**  
这包括姓名、透析号、电话、诊断细节、治疗备注、出生日期、真实排班截图，以及任何可能识别患者或医护人员的信息。

**[English]**  
This includes names, dialysis IDs, phone numbers, diagnosis details, treatment notes, dates of birth, real schedule screenshots, or any information that could identify a patient or staff member.

## 漏洞反馈 / Reporting Security Issues

**[中文]**  
如果你发现隐私或安全问题，请通过邮件私下反馈：

**[English]**  
If you find a privacy or security issue, please report it privately by email:

`434881918@qq.com`

**[中文]**  
反馈时请尽量包含：问题简述、复现步骤、受影响文件或功能、是否可能暴露真实数据、你建议的修复方式。

**[English]**  
Please include a short description, reproduction steps, affected files or features, whether real data could be exposed, and any suggested mitigation.

**[中文]**  
请不要为涉及患者隐私或敏感数据的问题创建公开 issue。

**[English]**  
Please do not open a public issue for vulnerabilities involving patient privacy or sensitive data.

## 当前安全模型 / Current Security Model

**[中文]**

- 项目是静态浏览器应用。
- 不需要后端服务器。
- 不需要数据库。
- 程序不会自动上传数据。
- 默认数据保存在浏览器 `localStorage` 中。
- 用户可以导出和导入 JSON 备份。

**[English]**

- The project is a static browser application.
- No backend server is required.
- No database is required.
- The application does not automatically upload data.
- Data is stored in browser `localStorage` by default.
- Users can export and import JSON backups.

## 使用建议 / Recommended Practices

**[中文]**

- 测试时使用假数据或匿名数据。
- 不上传包含真实患者姓名的截图。
- 只把备份文件保存到可信设备。
- 共用电脑前清理本地数据。
- 医疗机构正式使用前，应由科室、护理管理、院感、信息和隐私部门共同审核。

**[English]**

- Use fake or anonymized data for testing.
- Do not upload screenshots with real patient names.
- Export backups only to trusted devices.
- Clear local data before sharing a computer.
- Before institutional use, review the project with clinical, nursing, infection-control, IT, and privacy teams.

## 医疗安全声明 / Medical Safety Disclaimer

**[中文]**  
Dialysis-Scheduler 不是医疗诊断系统、治疗建议系统或经过认证的临床决策系统。它只是排班辅助工具。所有排班结果都必须由合格医护人员人工复核后再执行。

**[English]**  
Dialysis-Scheduler is not a medical diagnosis system, treatment recommendation system, or certified clinical decision system. It is a scheduling-assistance tool. All generated schedules must be reviewed and approved by qualified healthcare staff before use.

