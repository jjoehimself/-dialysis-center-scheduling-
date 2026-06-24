# Roadmap / 路线图

> [中文] 本路线图关注安全性、可复核性、隐私保护和中小型血透室的本地可用性。  
> [English] This roadmap focuses on safety, reviewability, privacy, and local usability for small and mid-sized dialysis units.

## 近期计划 / Near Term

**[中文]**

- 增加排班规则的自动化回归测试。
- 增加仅包含假数据的示例 JSON 备份文件。
- 增加常用流程截图和操作说明。
- 改进英文文档，并保持中英文内容同步。
- 使用假数据创建 GitHub Pages 在线演示。
- 增加更清晰的首次使用引导。
- 在重置或清空缓存前增加导出备份提醒。

**[English]**

- Add automated regression tests for scheduling rules.
- Add sample JSON backup files with fake data only.
- Add screenshots and workflow documentation.
- Improve English documentation and keep it aligned with Chinese content.
- Create a GitHub Pages demo using fake data only.
- Add a clearer first-run guide.
- Add export reminders before reset or cache clearing.

## 排班可靠性 / Scheduling Reliability

**[中文]**

- 扩展 2 周循环排班的自检覆盖。
- 为无法生成排班的情况提供更清晰的阻止原因。
- 增加固定机位、暂停机器、月度血滤等边界测试。
- 增加重病区和传染区容量测试。
- 医护覆盖不完整时提供更清楚的警告。
- 改进重新生成排班后的差异报告。

**[English]**

- Expand self-check coverage for two-week cycles.
- Provide clearer blocking reasons when scheduling cannot be generated.
- Add edge-case tests for fixed seats, paused machines, and monthly hemofiltration.
- Add capacity tests for severe-care and infection zones.
- Provide clearer warnings when staff coverage is incomplete.
- Improve schedule-difference reports after regeneration.

## 隐私与机构使用准备 / Privacy And Institutional Readiness

**[中文]**

- 补充真实医疗环境中的隐私实践建议。
- 设计可选的本地备份流程。
- 设计可选的审计日志方案。
- 设计可选的角色权限方案。
- 增加院内信息部门审核指南。
- 为截图和公开 issue 增加隐私提醒。

**[English]**

- Document privacy practices for real healthcare environments.
- Design an optional local backup workflow.
- Design optional audit-log guidance.
- Design optional role-based access-control guidance.
- Add internal hospital IT review guidance.
- Add privacy reminders for screenshots and public issues.

## 可访问性与易用性 / Accessibility And Usability

**[中文]**

- 改进键盘操作。
- 改进屏幕阅读器标签。
- 检查所有主题的对比度。
- 简化报告文字，让非技术用户更容易理解。
- 优化打印版布局。
- 改进手机和平板显示效果。

**[English]**

- Improve keyboard navigation.
- Improve screen-reader labels.
- Review contrast in all themes.
- Simplify report wording for non-technical users.
- Improve compact print layouts.
- Improve mobile and tablet readability.

## 国际化 / Internationalization

**[中文]**

- 提高所有支持语言的翻译完整度。
- 增加翻译审核说明。
- 将临床术语和通用界面术语分开维护。
- 检查阿拉伯语、乌尔都语、波斯语、希伯来语等 RTL 布局。

**[English]**

- Improve translation completeness across all supported languages.
- Add translation review notes.
- Maintain clinical terms separately from general UI terms.
- Check RTL layouts for Arabic, Urdu, Persian, and Hebrew.

## 开源维护 / Open Source Maintenance

**[中文]**

- 增加 issue 模板。
- 增加 pull request 模板。
- 增加项目架构说明。
- 为复杂排班逻辑补充必要注释。
- 为每个稳定版本补充发布说明。
- 增加手动 QA 检查清单。

**[English]**

- Add issue templates.
- Add pull request templates.
- Add a project architecture document.
- Add necessary comments around complex scheduling logic.
- Add release notes for each stable version.
- Add a documented manual QA checklist.

