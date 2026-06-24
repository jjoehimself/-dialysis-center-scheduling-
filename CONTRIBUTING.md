# Contributing / 贡献指南

> [中文] 感谢你愿意帮助改进 Dialysis-Scheduler。  
> [English] Thank you for helping improve Dialysis-Scheduler.

## 项目原则 / Project Principles

**[中文]**

- 免费开源。
- 默认本地优先。
- 不自动上传患者数据。
- 真实使用前必须人工复核。
- 排班规则要清晰、保守、可解释。

**[English]**

- Free and open source.
- Local-first by default.
- No automatic patient-data upload.
- Human review before real-world use.
- Scheduling rules should be clear, conservative, and explainable.

## 开始之前 / Before You Start

**[中文]**  
开发、测试、提交 bug、上传截图时，请不要使用真实患者数据。请使用假姓名、假透析号、假电话和假排班。

**[English]**  
Please do not use real patient data while developing, testing, reporting bugs, or sharing screenshots. Use fake names, fake dialysis IDs, fake phone numbers, and fake schedules.

## 适合贡献的内容 / Good First Contributions

**[中文]**

- 改进文档。
- 使用假数据补充截图。
- 修正翻译。
- 改进无障碍标签。
- 增加排班规则回归测试。
- 改进报告文字。
- 修复 UI 问题。
- 增加 issue 模板。

**[English]**

- Improve documentation.
- Add screenshots using fake demo data.
- Correct translations.
- Improve accessibility labels.
- Add regression tests for scheduling rules.
- Improve report wording.
- Fix UI bugs.
- Add issue templates.

## 项目结构 / Project Structure

**[中文]**

- `index.html`：界面结构。
- `styles.css`：布局、主题、打印样式和报告样式。
- `app.js`：排班逻辑、状态管理、校验、导入导出和渲染。
- `languages.js`：支持语言和界面文本。

**[English]**

- `index.html`: UI structure.
- `styles.css`: layout, themes, print styles, and report styles.
- `app.js`: scheduling logic, state management, validation, import/export, and rendering.
- `languages.js`: supported languages and UI text.

## Pull Request 检查清单 / Pull Request Checklist

**[中文]**

- `index.html` 可以正常打开。
- 页面加载时浏览器控制台无错误。
- 演示数据可以生成。
- 自动排班可以生成复核报告。
- 排班自检可以运行。
- JSON 导出和导入可以运行。
- 没有包含真实患者数据。
- 修改用户可见文字时，同步更新语言文件。
- 用户可见变化同步更新 README 或 CHANGELOG。

**[English]**

- `index.html` opens correctly.
- No browser console error appears on load.
- Demo data can be generated.
- Automatic scheduling produces a review report.
- Safety self-check runs.
- JSON export and import work.
- No real patient data is included.
- User-facing text is updated in language files when needed.
- User-visible changes are documented in README or CHANGELOG.

## 修改排班规则 / Scheduling Rule Changes

**[中文]**  
排班规则涉及安全和实际工作流程。如果修改排班逻辑，请说明：修改了什么规则、为什么修改、影响哪些患者/机器/医护/分区场景、如何测试、是否影响固定机位、传染隔离、重病区容量或机型匹配。

**[English]**  
Scheduling rules affect safety and real workflows. If you change scheduling logic, please explain what changed, why it changed, which patient/machine/staff/zone cases are affected, how you tested it, and whether it affects fixed seats, infection isolation, severe-care capacity, or machine-type matching.

## 隐私规则 / Privacy Rule

**[中文]**  
不要提交真实患者资料、医护个人资料、医院真实排班或可识别截图。

**[English]**  
Never commit real patient data, staff personal data, hospital schedules, or identifiable screenshots.

