# 血透室排班系统 / Hemodialysis Room Scheduler

**版本 / Version: 2026.06.17.2 — Comprehensive Fix Release**

一个无需后端服务器、可直接在浏览器中运行的血透室患者、机器与医护排班工具。

A browser-based scheduler for dialysis patients, machines, doctors, and nurses. It runs locally with plain HTML, CSS, and JavaScript and requires no backend server or database.

---

## 中文

### 主要功能

- 患者、医生、护士资料管理。
- 上午、下午双班次排班。
- 周一至周六的长期周模板，以及仅影响指定日期的临时调整。
- 病人优先与医护优先两种自动排班策略。
- 长期固定机位；机器临时故障时可绕开，恢复后回到原固定机位。
- 普通区、重病区、通用传染区、HBC、HBV、HCV、T 分区。
- 血透、血滤、灌流三种严格固定机器类型。
- 自动医护排班、患者冲突检查、打印、JSON 导入与导出。
- 浏览器本地保存、中英文切换和“清空所有缓存”功能。

### 默认机器布局

默认布局为 **6 排 × 10 台，共 60 台机器**：

| 机器编号 | 默认类型与区域 |
|---|---|
| 1 | HBV 区血滤 |
| 2—7 | HBV 区血透 |
| 8 | HCV 区血透 |
| 9 | T 区血透 |
| 10 | T 区血滤 |
| 11、41、50、51 | 普通区血滤 |
| 21、30、31、40 | 重病区血滤 |
| 21—40 其余机器 | 重病区血透 |
| 其余机器 | 普通区血透 |

机器类型严格一一对应：血透只能使用血透机，血滤只能使用血滤机，灌流只能使用灌流机。

### 护士配置规则

- 重病区每 5 名当班患者配置 1 名责任护士。
- 其他区域每 6 名当班患者配置 1 名责任护士。
- 两类人数独立计算，不能互相抵扣。
- 每名责任护士最多负责 1 台血滤机。
- 同一责任护士的机位尽量连续、相邻。
- HBV、HCV、HBC、T 与通用传染区分别管理，不与普通区、重病区混组。
- 空班次不安排医护岗位。

### 排班策略

**病人优先**尽量保持患者原星期、班次和固定机位。  
**医护优先**尽量把患者集中到更少的开班日和班次，让医护获得更多完整休息班次，同时仍严格遵守所有机器、分区和护理规则。

### 长期固定机位与机器暂停

首次成功生成周模板后，未指定机位的患者会获得长期固定机位。临时换机应保存为“仅当前日期”，不会改变之后的周模板。

机器可以在布局设置中标记为暂停：

- 暂停不删除机器或固定关系。
- 自动排班会避开暂停机器。
- 恢复后重新生成排班即可回到固定机位。

### 月度血滤

- 仅常规血透患者可设置每月血滤次数。
- 月度血滤保存为未来 4 周的日期调整，不写入永久周模板。
- 再次生成周模板时会移除上一轮自动生成的月度血滤调整，避免重复累积。
- 人工创建的单日调整不会被自动清理。

### 数据与缓存

数据默认保存在浏览器 `localStorage` 中。

- **全部重置**：清空本程序业务数据并恢复默认状态。
- **清空所有缓存**：删除本程序数据与本程序专用浏览器缓存，并通过新 URL 参数重新载入页面；不会主动清除同一网站其他程序的数据。
- 导入前会验证 JSON 基本结构。
- 损坏的旧缓存会被安全移除并恢复默认数据。

建议在重置、清缓存或升级前先导出 JSON 备份。

### 快速开始

```text
index.html
app.js
styles.css
README.md
```

将这些文件放在同一目录，双击 `index.html` 即可使用。也可以部署到 GitHub Pages。

### 本次修复重点

- 修复缺失控件造成的启动错误。
- 恢复用户指定的 60 台默认布局。
- 修复机器类型错误兼容。
- 修复护士比例、血滤机数量和跨分区责任组错误。
- 修复空班次和多余护士岗位。
- 修复孤儿排班、无效机器记录与损坏缓存。
- 修复月度血滤自动调整重复累积。
- 增强布局、机器类型和分区修改前的兼容性校验。
- 增加安全范围的“清空所有缓存”按钮。
- 优化自动排班性能并清理不可达旧代码。

---

## English

### Key Features

- Patient, doctor, and nurse records.
- Morning and afternoon scheduling.
- Recurring Monday-to-Saturday templates and date-specific overrides.
- Patient-priority and staff-priority automatic scheduling modes.
- Long-term fixed machine assignments and temporary machine suspension.
- Standard, severe-care, shared-infection, HBC, HBV, HCV, and T zones.
- Strict hemodialysis, hemofiltration, and hemoperfusion machine modalities.
- Automatic staff scheduling, conflict checks, printing, and JSON import/export.
- Browser-local storage, Chinese/English UI, and application cache clearing.

### Default 60-Machine Layout

The default room contains **60 machines in 6 rows of 10**:

| Machines | Default modality and zone |
|---|---|
| 1 | HBV hemofiltration |
| 2–7 | HBV hemodialysis |
| 8 | HCV hemodialysis |
| 9 | T-zone hemodialysis |
| 10 | T-zone hemofiltration |
| 11, 41, 50, 51 | Standard-zone hemofiltration |
| 21, 30, 31, 40 | Severe-care-zone hemofiltration |
| Remaining machines from 21–40 | Severe-care-zone hemodialysis |
| All remaining machines | Standard-zone hemodialysis |

Machine modalities are strict: a hemodialysis session can only use a hemodialysis machine, a hemofiltration session can only use a hemofiltration machine, and a hemoperfusion session can only use a hemoperfusion machine.

### Nurse Staffing Rules

- Severe-care zone: 1 primary nurse per 5 assigned patients.
- All other zones: 1 primary nurse per 6 assigned patients.
- The two capacities are calculated independently.
- One primary nurse may cover no more than 1 hemofiltration machine.
- Machines assigned to one nurse are kept as compact and adjacent as possible.
- HBV, HCV, HBC, T, shared-infection, standard, and severe-care responsibility groups are not mixed.
- Empty shifts require no staff positions.

### Scheduling Priorities

**Patient priority** preserves patient day, shift, and fixed-machine preferences whenever possible.  
**Staff priority** concentrates treatments into fewer active days and shifts to create more complete rest periods for staff, while keeping all modality, zone, fixed-machine, and staffing constraints mandatory.

### Fixed Machines and Machine Suspension

After the first successful weekly schedule generation, patients without a selected machine receive a long-term fixed machine. A temporary move should be saved as a date-specific override so that later sessions return to the fixed position.

Suspending a machine:

- Keeps its number, modality, zone, and patient fixed-machine relationship.
- Excludes it from automatic scheduling.
- Allows patients to return after the machine is restored and the schedule is regenerated.

### Monthly Hemofiltration

- Monthly hemofiltration frequency applies only to patients whose regular modality is hemodialysis.
- Monthly HDF sessions are stored as date-specific overrides over a four-week cycle.
- Regenerating a weekly template removes the previous automatically generated monthly-HDF overrides before creating new ones.
- Manually created date overrides are preserved.

### Data and Cache Management

Application data is stored in browser `localStorage`.

- **Reset All** clears application records and restores defaults.
- **Clear App Cache** removes this application's records and app-owned browser storage, then reloads the page with a cache-busting URL. It does not intentionally remove storage owned by other applications on the same origin.
- Imported JSON is checked for a recognizable scheduler structure.
- Corrupted saved data is removed safely and the application starts with defaults.

Export a JSON backup before resetting, clearing cache, or upgrading.

### Quick Start

Keep these files in the same directory and open `index.html`:

```text
index.html
app.js
styles.css
README.md
```

No build process, Node.js, Python, or database is required. The project can also be deployed through GitHub Pages.

### Major Fixes in This Release

- Fixed startup failures caused by missing UI controls.
- Restored the requested 60-machine default layout.
- Removed incorrect cross-modality machine compatibility.
- Corrected nurse capacity, HDF-machine limits, compact grouping, and zone isolation.
- Removed false staff requirements on empty shifts and stale extra nurse slots.
- Cleaned orphan schedules, invalid machine records, and corrupted storage.
- Prevented automatically generated monthly-HDF overrides from accumulating.
- Added compatibility checks before layout, modality, or zone changes.
- Added safely scoped application cache clearing.
- Improved automatic scheduling performance and removed unreachable legacy code.

### Disclaimer

This project is a scheduling and demonstration tool, not a diagnostic or clinical decision-support system. Before production use in a healthcare institution, clinical, nursing, infection-control, privacy, security, backup, authentication, and audit requirements must be reviewed and implemented.


### 长期周模板 / Recurring Weekly Template

- “生成长期周模板建议”会生成周一至周六的完整排班，并保存为以后每周循环的长期模板。
- “本周设为长期模板”会把当前这一整周转换为长期模板，而不是只保存当前日期。
- “Generate Recurring Weekly Template” creates and saves a complete Monday-to-Saturday recurring schedule.
- “Set This Week as Recurring Template” promotes the entire displayed week, not only the selected day.
