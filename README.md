# Dialysis-Scheduler

> [中文] 面向血液透析室的隐私友好、本地优先、免费开源排班辅助工具。  
> [English] A privacy-friendly, local-first, free and open-source scheduling assistant for hemodialysis rooms.

---

## 项目简介 / Project Overview

**[中文]**  
Dialysis-Scheduler 是一个面向血液透析室的本地排班辅助系统。它使用原生 HTML、CSS、JavaScript 编写，直接在浏览器中运行，不需要服务器、数据库、账号系统或网络连接。患者资料、医护资料、机器布局、长期模板和单日调整默认保存在当前电脑浏览器本地。

**[English]**  
Dialysis-Scheduler is a local scheduling assistant for hemodialysis rooms. It is built with plain HTML, CSS, and JavaScript, and runs directly in the browser without a server, database, account system, or internet connection. Patient records, staff records, machine layouts, recurring templates, and date-specific adjustments stay on the local computer by default.

---
<img width="915" height="1810" alt="image" src="https://github.com/user-attachments/assets/29105663-415a-4ef7-889f-e0cfa6b91754" />
<img width="955" height="1780" alt="image" src="https://github.com/user-attachments/assets/e1cec173-b33b-4e75-be0b-800853873fb1" />
<img width="1890" height="1390" alt="image" src="https://github.com/user-attachments/assets/14687b28-904d-49e6-a5b2-aa330a5a200f" />

## 为什么做这个项目 / Why This Project Matters

**[中文]**  
血透室排班不是简单的日历问题。真实场景中需要同时处理患者透析频率、固定机位、上午/下午班次、传染病隔离、重病区、机器故障、血透/血滤/灌流机型匹配、护士责任区、医生覆盖和临时调整。很多中小型或资源有限的透析单位仍然依靠手工方式处理这些复杂约束。

**[English]**  
Hemodialysis scheduling is not just a calendar problem. Real dialysis rooms must consider patient frequency, fixed machine positions, morning and afternoon shifts, infection isolation, severe-care areas, machine failures, treatment-machine compatibility, nurse responsibility zones, doctor coverage, and temporary changes. Many small or resource-limited dialysis units still handle these constraints manually.

**[中文]**  
本项目由透析患者创建，希望在保留人工复核和安全规则的前提下，帮助血透室减少重复排班工作，让患者固定机位更清晰，也让医护排班更容易检查和调整。

**[English]**  
This project was created by a dialysis patient. Its goal is to reduce repetitive scheduling work, make fixed patient seats easier to manage, and give healthcare staff a clearer way to review and adjust schedules while keeping human review and safety rules in place.

---

## 核心特点 / Key Features

**[中文]**

- 纯本地浏览器运行，打开 `index.html` 即可使用。
- 患者库、医护库、机器布局管理。
- 患者长期固定机位。
- 长期 2 周循环排班。
- 上午、下午独立班次。
- 患者优先、医护优先、灵巧排班三种策略。
- 血透、血滤、灌流机型严格匹配。
- 普通区、重病区、通用传染区、HBV、HCV、HBC、T 区隔离。
- 重病区 5 名患者配置 1 名护士。
- 其他区域 6 名患者配置 1 名护士。
- 每名责任护士最多负责 1 台血滤机。
- 护士责任区不跨越物理机器排。
- 机器故障暂停与恢复。
- 临时插入患者，不移动已排好的患者。
- 智能调班，适合请假和短期替班。
- 排班自检和人工复核报告。
- 打印排班和复核报告。
- JSON 导入、导出和备份。
- 演示数据生成，便于测试和培训。
- 多语言界面，支持 LTR 和 RTL 语言。
- 明亮、护眼绿、暗黑主题。

**[English]**

- Fully local browser app: open `index.html` and use it without a backend.
- Patient, staff, and machine management.
- Long-term fixed machine positions for patients.
- Two-week recurring scheduling cycle.
- Separate morning and afternoon shifts.
- Patient Priority, Staff Priority, and Smart Scheduling modes.
- Strict treatment-machine matching for hemodialysis, hemofiltration, and hemoperfusion.
- Standard, severe-care, shared infection, HBV, HCV, HBC, and T-zone separation.
- Severe-care nurse ratio: 1 nurse per 5 patients.
- Standard-area nurse ratio: 1 nurse per 6 patients.
- No more than 1 hemofiltration machine per responsible nurse.
- Nurse responsibility zones kept within physical machine rows.
- Machine pause and failure handling.
- Temporary patient insertion without moving existing patients.
- Smart staff shift swapping for leave and short-term coverage.
- Safety self-check and human review reports.
- Printable schedules and review reports.
- JSON import, export, and backup.
- Demo data generation for testing and training.
- Multilingual UI, including LTR and RTL language support.
- Light, eye-comfort, and dark themes.

---

## 快速开始 / Quick Start

**[中文]**

1. 下载项目全部文件。
2. 确认以下文件在同一个文件夹：
   - `index.html`
   - `app.js`
   - `styles.css`
   - `languages.js`
3. 双击打开 `index.html`。
4. 设置机器布局、患者、医护和排班策略。
5. 生成排班，复核报告，然后导出 JSON 备份。

**[English]**

1. Download all project files.
2. Keep these files in the same folder:
   - `index.html`
   - `app.js`
   - `styles.css`
   - `languages.js`
3. Double-click `index.html`.
4. Configure the machine layout, patients, staff, and scheduling strategy.
5. Generate a schedule, review the report, then export a JSON backup.

---

## 本地隐私设计 / Local-First Privacy Design

**[中文]**  
程序不会自动上传患者或医护数据。默认数据保存在当前电脑浏览器的 `localStorage` 中。使用前建议定期导出 JSON 备份；不要在 GitHub issue、公开截图或演示文件中包含真实患者信息。

**[English]**  
The application does not automatically upload patient or staff data. By default, data is stored in the current browser's `localStorage` on the local computer. Users should export JSON backups regularly and never include real patient information in GitHub issues, public screenshots, or demo files.

**[中文]**  
医疗机构正式使用前，应补充账号权限、审计日志、安全备份、院内数据库方案和隐私保护流程，并由科室、护理管理、院感、信息部门共同审核。

**[English]**  
Before institutional use, the project should be reviewed by clinical, nursing, infection-control, IT, and privacy teams. Account permissions, audit logs, secure backups, internal database policies, and privacy procedures should be added where required.

---

## 排班规则 / Scheduling Rules

### 机型匹配 / Machine-Type Matching

**[中文]**  
治疗类型和机器类型是硬性规则，不会自动混用。

**[English]**  
Treatment-machine compatibility is treated as a hard rule. The system does not silently mix machine types.

| 治疗类型 / Treatment | 必须使用的机器 / Required Machine |
|---|---|
| 血透 / Hemodialysis | 血透机 / Hemodialysis machine |
| 血滤 / Hemofiltration | 血滤机 / Hemofiltration machine |
| 灌流 / Hemoperfusion | 灌流机 / Hemoperfusion machine |

### 分区隔离 / Zone Separation

**[中文]**  
系统支持普通区、重病区、通用传染区，以及 HBV、HCV、HBC、T 等独立传染分区。传染患者只能进入匹配的传染区或通用传染区，非传染患者不会进入传染区。

**[English]**  
The system supports standard zones, severe-care zones, shared infection zones, and separate HBV, HCV, HBC, and T zones. Infectious patients must be assigned to compatible infection zones or shared infection zones. Non-infectious patients are kept out of infection zones.

### 医护规则 / Staff Rules

**[中文]**

- 有患者的班次需要医生覆盖。
- 有患者的班次按患者数量配置责任护士。
- 可安排后备护士。
- 同一班次责任护士不能重复。
- 后备护士不能同时作为同一班次责任护士。
- 护士管区会检查人数、物理排、重病区容量和血滤机数量。

**[English]**

- Active shifts require doctor coverage.
- Active shifts require responsible nurses based on patient load.
- Backup nurses can be assigned.
- Responsible nurses must not be duplicated in the same shift.
- A backup nurse must not also be a responsible nurse in the same shift.
- Nurse groups are checked for load, row boundaries, severe-care capacity, and hemofiltration-machine count.

---

## 自检与人工复核 / Self-Check And Human Review

**[中文]**  
排班自检会检查漏排、同日重复安排、治疗和机器不匹配、传染分区不匹配、重病区容量问题、暂停机器仍被使用、无效医护引用、医生/护士/后备护士缺失、长期固定机位冲突等问题。

**[English]**  
The self-check report looks for missing sessions, duplicate same-day assignments, incompatible treatment and machine types, infection-zone mismatches, severe-care capacity problems, paused machines still being used, invalid staff references, missing doctor/nurse/backup coverage, and fixed-machine conflicts.

**[中文]**  
自检报告用于帮助护士长和医护人员复核，不代表自动批准排班。

**[English]**  
The self-check report is designed to support human review. It does not automatically approve a schedule.

---

## 截图建议 / Recommended Screenshots

**[中文]**  
提交开源支持、公益项目或项目介绍时，建议在 `docs/images/` 中加入以下截图：

**[English]**  
For open-source support applications, nonprofit presentations, or project documentation, it is recommended to add these screenshots under `docs/images/`:

- 主排班台 / Main schedule board
- 2 周排班报告 / Two-week schedule review report
- 患者库 / Patient library
- 医护排班 / Staff schedule board
- 机器布局设置 / Machine layout editor
- 排班自检报告 / Safety self-check report

---

## 项目状态 / Project Status

**[中文]**  
本项目正在持续开发中，适合本地测试、流程探索和开源协作。正式用于医疗机构前，必须由相关负责人进行制度、隐私、安全和临床流程审核。

**[English]**  
This project is under active development. It is suitable for local testing, workflow exploration, and open-source collaboration. Before use in a real healthcare institution, it must be reviewed for policy, privacy, security, and clinical workflow requirements.

---

## 路线图 / Roadmap

**[中文]**  
后续计划请查看 `ROADMAP.md`。

**[English]**  
See `ROADMAP.md` for planned improvements.

---

## 贡献 / Contributing

**[中文]**  
欢迎提交 issue 和 pull request。请先阅读 `CONTRIBUTING.md`。公开交流中请勿包含任何真实患者身份信息、联系方式、病历内容、真实排班截图或可识别资料。

**[English]**  
Issues and pull requests are welcome. Please read `CONTRIBUTING.md` first. Do not include real patient identity information, contact details, medical records, real schedule screenshots, or identifiable data in public discussions.

---

## 安全 / Security

**[中文]**  
隐私与漏洞反馈请查看 `SECURITY.md`。

**[English]**  
Please read `SECURITY.md` for privacy and vulnerability reporting guidance.

---

## 医疗免责声明 / Medical Disclaimer

**[中文]**  
Dialysis-Scheduler 是排班辅助工具，不是医疗诊断系统，不是治疗建议系统，也不是经过认证的临床决策系统。所有排班结果必须由合格医护人员人工复核后再执行。

**[English]**  
Dialysis-Scheduler is a scheduling-assistance tool. It is not a medical diagnosis system, treatment recommendation system, or certified clinical decision system. All generated schedules must be reviewed and approved by qualified healthcare staff before use.

---

## 许可证 / License

**[中文]**  
本项目使用 MIT License。

**[English]**  
This project is released under the MIT License.
