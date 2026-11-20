# UI Design Directions

把「参考这些好看的产品」变成一次可以做决定的设计讨论。这个 Agent Skill 带着案例库和工具目录工作。它先研究参考界面，用同一份产品内容生成四版大图，让用户在一页内比较。用户选定方向后，才开始修改产品。

## 从哪里看起

- 想看产品功能怎么讲清楚？案例库里有 Apple Pages 的模板选择器、Stripe Press 的书籍详情，以及 Runmo 把曲线和读数放在一起的动效。[产品与界面案例](skills/ui-design-directions/references/cases.md)
- 想看用 AI 做出的实际作品？这里有作者的演示和可打开的项目，涵盖仪表盘、中文官网、文档、编辑器与交互动效。[X 上的公开作品](skills/ui-design-directions/references/x-cases.md)
- 想知道该用哪个 Skill？用 `taste` 读参考页面，用 `landing-page-design` 安排产品介绍，用 `emil-design-eng` 细化控件。每项都写明了来源和适用环节。[Skills 与工具](skills/ui-design-directions/references/tools.md)

## 安装

在项目目录运行以下命令。需要让多个项目共用时，在命令末尾加 `-g`。

```sh
npx skills add zhou2ding/ui-design-directions --skill ui-design-directions
```

主 Skill 包含流程和全部参考资料。要运行网页逆向，再按工具目录配置 `taste` 和 Playwright MCP。其余设计 Skills 按任务选用，无需一次装齐。

## 如何调用

**产品官网**

> 用 $ui-design-directions 为我们的研究软件做官网方案。优先参考 Apple。访客需要看懂产品能做什么，每个主要功能都要有清晰的实际界面。先把四版大图放在一页给我看。

**已有客户端**

> 用 $ui-design-directions 提升桌面客户端的质感。保留现有布局、业务流程和按钮位置。请用同一个工作界面比较四套字体、色彩和控件样式，放大展示选中态、按钮和浮层。

**补充案例**

> 用 $ui-design-directions 更新案例库。这几条是我最近在 X 转发的设计作品。找到原作者和演示，告诉我哪些值得收录、分别值得看什么。

[完整流程](skills/ui-design-directions/SKILL.md) · [案例收录规则](skills/ui-design-directions/references/update-cases.md) · [MIT 许可证](LICENSE)

MIT 许可适用于本仓库的原创内容。案例图片、视频、字体和第三方 Skills 由各自权利人授权，仓库提供原始链接。
