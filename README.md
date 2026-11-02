# SleepShift · 睡眠节奏

纯 HTML/CSS/JavaScript 的 iPhone 友好 PWA，沿用 `vook-tire` 的 GitHub Pages + manifest + Service Worker 技术路线。无需 npm、构建工具、服务器或本地电脑。所有时间均使用北京时间（Asia/Shanghai）。

## 功能

- 2026-11-02 起四周、每天的渐进睡眠计划；第 4 周后按最终节奏维持
- 工作日、周五居家办公、周六/周日早骑的不同起床计划及设置
- 睡前流程时间自动倒推：结束游戏、调暗灯光、有睡意再上床、理想入睡
- 独立睡眠预算计算器（实际睡眠目标、夜醒、入睡等待、次日起床）
- 睡前清单、手动睡眠日志、最近七晚均值和 JSON 导入导出
- 无外部 CDN、支持离线访问、iOS 主屏幕独立模式

## 在线部署（GitHub Pages）

1. 创建一个名为 `sleep-shift` 的新 GitHub 仓库（如果使用免费的 GitHub Pages，请选择 Public）。
2. 上传本项目根目录下全部文件，或从 ChatGPT 中通过已连接的 GitHub 连接器写入该仓库。
3. GitHub 仓库打开 **Settings → Pages → Build and deployment → Deploy from a branch → main → /(root) → Save**。
4. Pages 完成部署后，网页通常位于 `https://<username>.github.io/sleep-shift/`，实际以 GitHub Pages 设置显示的 URL 为准。
5. 在 iPhone Safari 中打开部署后的 HTTPS URL，点共享 → 添加到主屏幕 → 作为网页 App 打开。

## 重要边界

- **不是 Apple Health 自动同步工具**。普通 GitHub Pages PWA 无法直接访问 Apple Health/HealthKit，需要额外原生应用、快捷指令或后端才可能安全同步。
- 默认作息与计划属于仓库公开代码内容；个人睡眠日志、用户自定义设置、打卡记录只保存在当前设备本地 `localStorage`，不会写到 GitHub。
- 本地数据没有跨设备同步；清除网站数据/卸载网页 App 可能丢失，需自行导出 JSON 备份。Safari 与已添加到主屏幕的网页 App 可能使用不同存储容器。
- 更改聊天中的计划不会**自动**更新 GitHub；后续可在 ChatGPT 中通过 GitHub 连接器提交代码变更并重新发布。
- 时间计算仅用于计划，不是治疗建议；睡不着时应避免强迫自己躺床。

## 文件

- `index.html`：完整交互逻辑与样式，无第三方依赖。
- `manifest.webmanifest`：iOS / PWA 安装配置。
- `sw.js`：离线缓存与上线后优先检查更新。
- `icon-192.png` / `icon-512.png`：App 图标。
- `.nojekyll`：GitHub Pages 静态资源配置。
