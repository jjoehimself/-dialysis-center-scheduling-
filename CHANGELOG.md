# Changelog / 更新日志

> [中文] 这里记录用户可见变化，避免 README 变成过长的开发记录。  
> [English] This file tracks user-visible changes so the README does not become an overly long development log.

## Unreleased / 未发布

**[中文]**

- 重写项目文档，使其更适合开源审核和公益项目介绍。
- 增加更清晰的本地优先和隐私说明。
- 增加路线图、安全政策和贡献指南。
- 增强医疗使用前必须人工复核的说明。

**[English]**

- Reorganized project documentation for open-source review and public-interest presentation.
- Added clearer local-first and privacy guidance.
- Added roadmap, security policy, and contribution guide.
- Strengthened the disclaimer that medical use requires human review.

## 当前稳定方向 / Current Stable Direction

**[中文]**

- 浏览器本地运行，无需后端。
- 患者、医护、机器管理。
- 默认 60 台机器布局。
- 患者长期固定机位。
- 长期 2 周循环排班。
- 传染区和重病区隔离。
- 血透、血滤、灌流机型严格匹配。
- 机器暂停和临时调整。
- 护士容量检查。
- 排班自检和打印复核报告。
- JSON 导入、导出和备份。
- 多语言界面和主题支持。

**[English]**

- Browser-only operation with no backend requirement.
- Patient, staff, and machine management.
- Default 60-machine layout.
- Long-term fixed patient seats.
- Two-week recurring scheduling.
- Infection-zone and severe-care separation.
- Strict hemodialysis, hemofiltration, and hemoperfusion machine matching.
- Machine pause and temporary adjustment handling.
- Nurse-capacity checks.
- Self-check and printable review reports.
- JSON import, export, and backup.
- Multilingual UI and theme support.

## 安全相关改进 / Safety-Oriented Improvements

**[中文]**

- 保存自动生成排班前增加硬性安全审计。
- 增加同一患者同日重复安排检测。
- 增加暂停机器校验。
- 增加治疗和机型兼容校验。
- 增加传染分区校验。
- 增加固定机位校验。
- 增加护士容量校验。
- 增加每名护士最多负责一台血滤机校验。
- 增加医生、责任护士和后备护士校验。
- 导入数据时对未来排班进行安全校验。

**[English]**

- Added hard checks before saving generated schedules.
- Added duplicate same-day patient assignment detection.
- Added paused-machine validation.
- Added treatment-machine compatibility validation.
- Added infection-zone validation.
- Added fixed-seat validation.
- Added nurse capacity validation.
- Added validation for no more than one hemofiltration machine per nurse.
- Added doctor, responsible nurse, and backup nurse validation.
- Added import-time safety validation for future schedules.

## 界面与流程改进 / UI And Workflow Improvements

**[中文]**

- 增加 2 周循环排班流程。
- 增加当前 2 周报告生成。
- 增加排班自检。
- 增加临时插入患者。
- 增加智能调班。
- 增加撤销快照。
- 增加长任务进度提示。
- 增加打印报告。
- 增加明亮、护眼绿和暗黑主题。
- 增加多语言界面支持。

**[English]**

- Added two-week cycle workflow.
- Added current two-week report generation.
- Added schedule self-check.
- Added temporary patient insertion.
- Added smart shift swapping.
- Added undo snapshots.
- Added progress indicators for long-running actions.
- Added printable reports.
- Added light, eye-comfort, and dark themes.
- Added multilingual UI support.

