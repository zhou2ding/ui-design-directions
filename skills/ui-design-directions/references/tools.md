# 逆向分析与 UI 设计 Skills

开工时先查看当前宿主能调用哪些 Skills，按各自的 `SKILL.md` 执行。这里的 GitHub 链接指向原维护者。下列安装命令使用 Skills CLI，运行环境和第三方依赖按上游说明配置。

## 从真实页面提取设计依据

| 工具 | 如何使用 |
| --- | --- |
| [`taste` · senlindesign/taste-skill](https://github.com/senlindesign/taste-skill) | 提供页面 URL，采集实渲染的截图和 DOM。读取输出的 Markdown 与 JSON，对照字体、间距、圆角、颜色用途等细节，说明它们服务于什么内容。对关键状态单独采样 |
| [Playwright MCP](https://github.com/microsoft/playwright-mcp) | `taste` 依赖的浏览器工具。先确认当前宿主已连接，可导航、截图和读取 DOM。若未就绪，按上游为当前宿主配置后再运行逆向分析 |

```sh
npx skills add senlindesign/taste-skill --skill taste
```

网页只能看到封面、视频或登录页时，说明看到了什么。若用户直接给了截图，可以先完成视觉观察，将字体、时长和间距的估计与 DOM 实测区别标注。

## 按设计问题选 Skill

| 设计问题 | 选用的 Skill | 期望得到什么 |
| --- | --- | --- |
| 官网从哪里开始介绍产品 | [`landing-page-design`](https://github.com/elayadesign/ai-design-skills) | 定下访客任务、功能概览、滚动场景和相关操作的顺序 |
| 四个方向怎样发展成完整概念 | [`frontend-design`](https://github.com/anthropics/skills) 或 [`design-taste-frontend`](https://github.com/Leonxlnx/taste-skill) | 选一项主导构图、材料及视觉节奏，做四个能看出差别的方案 |
| 控件和页面看上去像拼模板 | [`impeccable`](https://github.com/pbakaus/impeccable) | 用 `clarify` 检查文案，在修改预览 UI 前读 `craft-floor`，逐项看边缘、对齐、留白和组件的一致性 |
| 按钮按下、菜单浮起或面板过渡缺少层次 | [`emil-design-eng`](https://github.com/emilkowalski/skills) | 对照静止与操作时的状态，细化位移、阴影和过渡 |
| 字号太小或中文读起来累 | [`better-typography`](https://github.com/jakubkrehel/skills) | 逐级核对标题、说明和界面标签的字号、行距、换行与窄屏表现 |
| 功能介绍读起来空泛 | [`copywriting`](https://github.com/coreyhaines31/marketingskills) | 用用户能完成的动作和能得到的结果写短句，搭配可验证该能力的画面 |
| 需要比较配色、状态和组件搭配 | [`ui-ux-pro-max`](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) | 对比候选组合，再放到真实界面里看文字对比度及强调色的用途 |
| 方案选定后检查成品 | [`web-design-guidelines`](https://github.com/vercel-labs/agent-skills) | 检查语义、键盘焦点、交互与可访问性，再用实际浏览器验证 |
| 已确定需要一段可编辑的视频动效 | [`openmotion`](https://github.com/nexu-io/openmotion) | 按上游配置 Studio 和 MCP，制作关键画面与动画。普通按钮反馈可直接用 CSS 演示 |

网页逆向用的 `taste` 和制作界面的 `design-taste-frontend` 来自不同仓库。安装时核对维护者与 Skill 名称。下面是按单个 Skill 安装的例子，其他行同样可先用 `npx skills add 所有者/仓库 --list` 查看可用名称。

```sh
npx skills add elayadesign/ai-design-skills --skill landing-page-design
npx skills add pbakaus/impeccable --skill impeccable
npx skills add emilkowalski/skills --skill emil-design-eng
```

**搭配示例。** 产品官网可用 `taste` 研究 Apple Pages，再由 `landing-page-design` 组织讲解，`better-typography` 复核手机正文。固定布局的客户端可用 `taste` 研究 Primer 和 Spectrum 的同类控件，再由 `impeccable` 与 `emil-design-eng` 调整按钮、菜单与选中态。交付时说明实际调用了哪些，哪些观察来自人工查看。
