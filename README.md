我是一个透析患者上次，偶然看见透析室的医护还在用纸和笔排版，所以想提供点帮助。 :D


# 血透室排班系统 / Hemodialysis Room Scheduler

一个无需服务器、可直接在浏览器中运行的血透室患者、机器与医护排班工具。

A browser-based scheduling tool for dialysis patients, machines, doctors, and nurses. It runs locally without a server or database.

---

## 中文说明

### 项目简介

本项目是一套纯前端血透室排班系统，使用原生 HTML、CSS 和 JavaScript 开发。下载后直接打开 `index.html` 即可使用，也可以部署到 GitHub Pages 或院内静态服务器。

系统支持患者资料管理、医护人员管理、机器布局设置、周排班模板、单日临时调整、自动排班建议、传染病分区、重病区护理比例，以及数据导入、导出和打印。

### 主要功能

* 患者、医生、护士资料独立管理。
* 上午、下午双班次排班。
* 周一至周六使用周模板，周日默认休息。
* 支持仅当前日期的临时调整，不影响周模板。
* 支持复制前一天排班、清空当日排班和打印。
* 自动检测同一患者在同一班次的重复安排。
* 数据自动保存在浏览器 `localStorage` 中。
* 支持 JSON 数据导入与导出。
* 支持中文和英文界面切换。
* 机器排班卡片自动等高对齐，上午、下午区域保持整齐。

### 默认机器布局

默认布局为 **6 排 × 10 台，共 60 台机器**：

| 机器编号        | 默认区域与类型 |
| ----------- | ------- |
| 1           | HBV 区血滤 |
| 2—7         | HBV 区血透 |
| 8           | HCV 区血透 |
| 9           | T 区血透   |
| 10          | T 区血滤   |
| 11、41、50、51 | 普通区血滤   |
| 21、30、31、40 | 重病区血滤   |
| 21—40 其余机器  | 重病区血透   |
| 其他机器        | 普通区血透   |

所有机器均可在布局设置中重新指定为：

* 血液透析
* 血液滤过
* 血液灌流

机器区域可设置为：

* 普通区
* 重病区
* 通用传染区
* HBC 区
* HBV 区
* HCV 区
* T 区

### 分区规则

* 普通区和重病区均属于非传染区域，机器可互相调配。
* 自动排班时，普通患者优先进入普通区，严重组患者优先进入重病区。
* 当对应区域容量不足时，普通区与重病区可以跨区使用。
* 传染病区与非传染区严格隔离。
* 感染患者只能进入对应感染区或通用传染区。
* 非感染患者不会被安排到传染病专用机器。

### 护士配置规则

系统按照当班实际排入的患者和机器区域分别计算责任护士数量：

* **重病区：每 5 名患者配置 1 名责任护士。**
* **其他区域：每 6 名患者配置 1 名责任护士。**
* 两类患者分别向上取整计算，不混合抵扣。
* 每个班次默认配置 2 名医生。
* 每个班次另设 1 名后备护士。

示例：

* 重病区 20 人：需要 4 名责任护士。
* 其他区域 40 人：需要 7 名责任护士。
* 合计需要 11 名责任护士、2 名医生和 1 名后备护士。

### 自动排班

自动排班会综合考虑：

* 患者每周治疗次数
* 常用班次
* 透析星期倾向
* 治疗类型
* 普通组或严重组
* 感染标识
* 机器类型与机器区域
* 当班机器容量
* 医护岗位数量
* 医护人员上班倾向

当原日期或原班次容量不足时，系统会尝试调整到周一至周六的其他可用日期。硬性条件无法满足时，系统会提示具体缺口并停止保存。

### 血滤安排

* 患者可单独设置每月血滤次数。
* 默认每周 3 次治疗、每月 1 次血滤。
* 每月血滤会作为未来 4 周的单日调整生成。
* 血滤安排不会直接写入每周模板，避免每周重复执行。
* 血滤机在没有血滤任务时可以承担普通血透。

### 演示数据

系统可一键生成演示患者和演示医护人员，并可分别设置以下感染患者数量：

* HBC
* HBV
* HCV
* T

四类感染患者数量之和不能超过演示患者总数。

### 快速开始

1. 下载或克隆本项目。
2. 保持以下文件位于同一目录：

```text
index.html
app.js
styles.css
README.md
```

3. 双击打开 `index.html`。
4. 首次使用时进入“布局设置”，确认机器布局。
5. 在“患者库”和“医护库”中录入资料。
6. 返回“排班台”生成或手动调整排班。

无需安装 Node.js、Python、数据库或其他运行环境。

### GitHub Pages 部署

本项目是静态网页，可直接部署到 GitHub Pages：

1. 将项目上传到 GitHub 仓库。
2. 打开仓库的 `Settings`。
3. 进入 `Pages`。
4. 选择要发布的分支和根目录。
5. 保存后等待 GitHub 生成访问地址。

注意：GitHub Pages 版本的数据仍保存在访问者本机浏览器中，不会自动在不同电脑或不同账号之间同步。

### 数据与隐私

当前版本不连接服务器，所有数据默认保存在当前浏览器的 `localStorage` 中。

这意味着：

* 清除浏览器数据可能导致排班资料丢失。
* 更换浏览器或电脑后，数据不会自动迁移。
* 建议定期使用“导出”功能备份 JSON 文件。
* 正式用于科室前，应增加账号权限、自动备份、日志审计、院内数据库和访问控制。

### 项目文件


.
├── index.html     # 页面结构
├── app.js         # 排班、患者、医护和数据逻辑
├── styles.css     # 页面布局与视觉样式
└── README.md      # 项目说明
```

### 使用说明与免责声明

本项目目前定位为排班管理与演示工具，不属于医疗诊断系统或临床决策支持系统。

正式投入医疗机构使用前，应由科室负责人、护理管理人员、院感人员和信息部门共同审核，并根据当地法律法规及医院制度完成权限、隐私、安全、备份和审计改造。

---

## English

### Overview

Hemodialysis Room Scheduler is a client-side scheduling application built with plain HTML, CSS, and JavaScript. It can be opened directly through `index.html` and does not require a server, database, Node.js, Python, or any additional runtime.

The application manages dialysis patients, machines, doctors, nurses, weekly schedules, date-specific adjustments, infection-control zones, severe-care staffing ratios, data backup, and printing.

### Key Features

* Separate patient, doctor, and nurse management.
* Morning and afternoon scheduling.
* Weekly templates from Monday to Saturday.
* Sunday is treated as a rest day by default.
* Date-specific adjustments without changing the recurring weekly template.
* Automatic weekly scheduling suggestions.
* Copy the previous day's schedule.
* Clear or print the current day's schedule.
* Duplicate-patient conflict detection within the same shift.
* Automatic local saving through browser `localStorage`.
* JSON import and export.
* Chinese and English interface support.
* Equal-height machine cards with aligned morning and afternoon sections.

### Default Machine Layout

The default layout contains **60 machines arranged in 6 rows of 10**:

| Machine                   | Default zone and modality       |
| ------------------------- | ------------------------------- |
| 1                         | HBV-zone hemofiltration         |
| 2–7                       | HBV-zone hemodialysis           |
| 8                         | HCV-zone hemodialysis           |
| 9                         | T-zone hemodialysis             |
| 10                        | T-zone hemofiltration           |
| 11, 41, 50, 51            | Standard-zone hemofiltration    |
| 21, 30, 31, 40            | Severe-care-zone hemofiltration |
| Other machines from 21–40 | Severe-care-zone hemodialysis   |
| All remaining machines    | Standard-zone hemodialysis      |

Each machine can be configured as:

* Hemodialysis
* Hemofiltration
* Hemoperfusion

Each machine can also be assigned to:

* Standard zone
* Severe-care zone
* Shared infection zone
* HBC zone
* HBV zone
* HCV zone
* T zone

### Zone Rules

* The standard and severe-care zones are both non-infectious zones and may share machines when necessary.
* Standard patients are assigned to the standard zone first.
* Severe-care patients are assigned to the severe-care zone first.
* If the preferred non-infectious zone is full, the scheduler may use capacity from the other non-infectious zone.
* Infectious and non-infectious machines remain strictly separated.
* Infectious patients may only use their matching infection zone or the shared infection zone.
* Non-infectious patients are not assigned to infection-dedicated machines.

### Nurse Staffing Rules

Nurse requirements are calculated separately according to the actual patients assigned during each shift:

* **Severe-care zone: 1 primary nurse for every 5 patients.**
* **All other zones: 1 primary nurse for every 6 patients.**
* The two groups are rounded up and calculated independently.
* Each shift includes 2 doctors by default.
* Each shift also includes 1 backup nurse.

Example:

* 20 severe-care patients require 4 primary nurses.
* 40 patients in other zones require 7 primary nurses.
* Total staffing: 11 primary nurses, 2 doctors, and 1 backup nurse.

### Automatic Scheduling

The automatic scheduler considers:

* Weekly treatment frequency
* Preferred shift
* Preferred treatment days
* Treatment modality
* Standard or severe-care status
* Infection flag
* Machine modality and zone
* Available machine capacity
* Required clinical staff positions
* Staff shift preferences

If the preferred date or shift is full, the scheduler can move treatment to another available day from Monday to Saturday. If a mandatory rule cannot be satisfied, the schedule is not saved and the system reports the capacity shortage.

### Hemofiltration Planning

* Monthly hemofiltration frequency can be configured per patient.
* The default plan is 3 treatments per week and 1 hemofiltration treatment per month.
* Monthly hemofiltration is generated as date-specific adjustments over a four-week cycle.
* It is not written directly into the recurring weekly template.
* Hemofiltration-capable machines may be used for standard hemodialysis when no hemofiltration treatment is scheduled.

### Demo Data

The application can generate demo patients and staff. Infection counts can be configured separately for:

* HBC
* HBV
* HCV
* T

The combined number of infectious demo patients cannot exceed the total demo-patient count.

### Quick Start

1. Download or clone the repository.
2. Keep the following files in the same directory:

```text
index.html
app.js
styles.css
README.md
```

3. Open `index.html` in a modern browser.
4. Review the machine layout under Settings.
5. Add patients and staff members.
6. Return to the scheduling page to generate or edit schedules.

No build process or dependency installation is required.

### GitHub Pages Deployment

Because this is a static application, it can be hosted through GitHub Pages:

1. Upload the project to a GitHub repository.
2. Open the repository `Settings`.
3. Select `Pages`.
4. Choose the publishing branch and root directory.
5. Save and wait for the public URL to be generated.

Data on the hosted version is still stored in each visitor's browser and is not automatically synchronized between devices or users.

### Data and Privacy

The current version does not connect to a backend server. All application data is stored locally in the browser through `localStorage`.

Therefore:

* Clearing browser data may remove all schedules and records.
* Data is not automatically transferred to another browser or computer.
* Regular JSON exports are recommended as backups.
* Production use should add authentication, role-based access, automatic backups, audit logs, secure institutional storage, and access control.

### Project Structure

```text
.
├── index.html     # User interface structure
├── app.js         # Scheduling, patient, staff, and storage logic
├── styles.css     # Layout and visual design
└── README.md      # Project documentation
```

### Disclaimer

This project is currently intended as a scheduling and demonstration tool. It is not a medical diagnostic system or clinical decision-support system.

Before use in a healthcare institution, the workflow, staffing rules, infection-control rules, privacy protection, security, backup strategy, and audit requirements should be reviewed by clinical, nursing, infection-control, and information-technology personnel.


## Data Notes

Data is automatically saved in the browser’s `localStorage` and is loaded by default the next time `index.html` is opened. Before formal deployment in a clinical department, it is recommended to implement account permission controls, automatic backup mechanisms, and internal hospital data storage protocols.
