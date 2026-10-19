# Kami (紙) — Editorial Paper Theme for Clash Verge Rev

> *"Good content deserves good paper."*
>
> 一款受 **[tw93/Kami](https://github.com/tw93/Kami)**（[kami.tw93.fun](https://kami.tw93.fun)）纸张排版美学启发的 **Clash Verge / Clash Verge Rev** 自定义 CSS 主题。摒弃玻璃拟态与荧光渐变，以四阶暖色实体纸张层次、克制的传统墨蓝色（`#1B365D`）与人文衬线字体，让日常网络代理工具呈现如纸质书籍与杂志般的温润阅读体验。

---

## ✨ 设计特点 (Highlights)

1. **四阶物理纸张明暗层级（4-Step Physical Paper Hierarchy）**
   严格遵循 Kami 的纸张明度阶梯——越浮起于表面的卡片越接近温润的象牙白，拒绝刺眼的 `#FFFFFF` 纯白与混浊的冷灰：
   - **Level 0 · 导航与弹窗栏 (`--sidebar-bg: #efede4`)**：暖亚麻色，锚定左侧导航栏与二级弹窗的顶栏/底栏。
   - **Level 1 · 主页面与弹窗画布 (`--parchment: #f5f4ed`)**：Kami 标志性暖羊皮纸画布。
   - **Level 2 · 浮起纸张卡片 (`--ivory: #faf9f5`)**：首页卡片、代理组、节点卡片、订阅卡片、设置面板以及二级弹窗内部列表，统一使用象牙白纸张配合 `1px solid #e2dfd5` 细边框。
   - **Level 3 · 卡片内嵌控件 (`--control-bg: #f2f0e6` / `--warm-sand: #e8e6dc`)**：下拉框、输入框、分段切换器采用微凹的暖沙色，形成清晰的「画布 → 卡片 → 控件」三层嵌套关系。

2. **单一墨蓝强调色（Single Ink Blue Accent, `≤ 5%` 面积法则）**
   全界面仅使用一种主强调色——传统墨蓝 **`#1B365D`**（`--brand`），配合低饱和纯色标签底色 `#E4ECF5`（`--tag-bg`）与激活卡片底色 `#EEF2F7`（`--brand-tint`）。

3. **人文衬线 + 等宽对齐数字排版（Editorial Typography）**
   - **UI 与正文**：优先调用英文衬线 `Charter` 与中文 **[仓耳今楷 (`TsangerJinKai02`)](https://github.com/tw93/Kami)** / `思源宋体 (Source Han Serif SC)`。左侧导航栏字号放大加粗（未选中 `15.5px / 600`，选中态 `16px / 700` 象牙白浮起卡片），层级一目了然。
   - **技术数据与表格**：实时网速、延迟数值、端口号、连接表与日志均采用 `JetBrains Mono` / `SF Mono` 等宽字体并开启 `tabular-nums` 等宽数字对齐，高速刷新时数值绝不抖动。

4. **全页面 & 二级弹窗深度适配（Deep Component Coverage）**
   - **代理组（Proxies）**：针对 `StickyVirtualList` 虚拟列表专门隔离吸顶样式，保持整页羊皮纸画布连贯不断层；在「规则」模式下自动为右侧悬浮快速跳转栏（`ProxyGroupNavigator`）预留独立边距，绝不压线。
   - **订阅配置（Profiles）**：完整覆盖顶部 URL 导入栏、订阅卡片选中态，以及底部的「全局扩展覆写配置」与「全局扩展脚本」卡片。
   - **连接表格（Connections）**：移除原生滚动容器突兀的左上圆角与双层叠加粗线，采用上下 `1px` 极细纸张分割线与通栏纸张表头。
   - **设置与所有二级弹窗（Settings & Secondary Modals）**：通过针对 React Portal（`.MuiDialog-paper`）的四级分层规则，让「界面设置」、「系统代理设置」、「Tun 模式」、「Clash 内核」、「热键设置」、「DNS 设置」及内置 **Monaco 代码编辑器** 均拥有与主页面一致的纸张卡片层次；同时修复了「启动脚本」透明输入框占位框与「语言设置」文字截断问题。
   - **深色模式自适应（Dark Mode Ready）**：当切换至深色模式时，自动映射为 Kami 官方的 `--deep-dark`（`#141413`）与 `--dark-surface`（`#2c2c29`）暖炭黑配色。

---

## 🎨 色彩规范 (Color Tokens)

| 层级 / 用途 | CSS 变量 | 色值 (Light) | 色值 (Dark) | 说明 |
| :--- | :--- | :--- | :--- | :--- |
| **Level 0 · 边栏与弹窗栏** | `--sidebar-bg` | `#efede4` | `#111110` | 左侧导航栏、弹窗标题栏与底栏 |
| **Level 1 · 页面主画布** | `--parchment` | `#f5f4ed` | `#141413` | 页面主背景、表头、弹窗画布 |
| **Level 2 · 浮起纸张卡片** | `--ivory` | `#faf9f5` | `#1d1d1b` | 代理组、节点、设置面板、弹窗内列表 |
| **Level 3 · 内嵌控件底色** | `--control-bg` | `#f2f0e6` | `#252523` | 下拉框、文本输入框、次要按钮 |
| **悬停控件 / 进度槽** | `--warm-sand` | `#e8e6dc` | `#2c2c29` | 按钮/菜单悬停态、进度条底槽 |
| **主强调色（墨蓝）** | `--brand` | `#1B365D` | `#3B6EA5` | 主按钮、开关激活态、选中文字 |
| **选中卡片微染底色** | `--brand-tint` | `#EEF2F7` | `#182332` | 激活的代理节点与当前订阅卡片 |
| **标签与徽章底色** | `--tag-bg` | `#E4ECF5` | `#1d2d42` | 节点数量 Chip、下拉菜单选中项 |
| **主文本（暖墨黑）** | `--near-black` | `#141413` | `#f5f4ed` | 标题、卡片正文 (`R ≈ G > B`) |
| **次级文本（暖深灰）** | `--dark-warm` | `#3d3d3a` | `#dcd9ce` | 侧栏未选中文字、次要正文 |
| **辅助说明（橄榄灰）** | `--olive` | `#504e49` | `#a6a295` | 副标题、表头文字、图标常规态 |
| **卡片与结构边框** | `--border` | `#e2dfd5` | `#2b2b28` | `1px` 实体纸张边缘分割线 |

---

## 🚀 安装与使用 (Installation)

1. 打开 **Clash Verge / Clash Verge Rev**。
2. 进入左侧 **设置 (Settings)** → **外观 / 主题模式**，建议选择 **浅色 (Light)** 以获得最纯正的 Kami 暖羊皮纸视觉效果。
3. 在设置页中找到 **CSS 注入 (`CSS Injection` / 自定义 CSS)**（或点击「界面设置」中的 CSS 编辑入口）。
4. 复制本仓库 [`kami-clash-verge.css`](./kami-clash-verge.css) 中的全部内容，粘贴至编辑器并点击 **保存 (Save)** 即可立即生效。

---

## 🛠️ 个性化微调 (Customization)

所有的色彩、字号与字体栈均集中在 [`kami-clash-verge.css`](./kami-clash-verge.css) 顶部的 `:root` 变量区，您可以按需修改：

- **更换正文字体**：修改 `--serif` 变量（例如将思源宋体或霞鹜文楷放在首位）。
- **调整左侧导航栏字号**：搜索 `.the-menu .MuiListItemButton-root .MuiListItemText-primary`，按喜好微调 `font-size: 15.5px` 与选中态的 `16px`。
- **更换主题强调色**：修改 `:root` 中的 `--brand`、`--brand-light`、`--tag-bg` 与 `--brand-tint` 即可一键切换整套主题的墨水色调。

---

## 🙏 致谢 (Credits)

- 设计灵感与配色体系源自 [@tw93](https://github.com/tw93) 的 **[Kami (紙)](https://github.com/tw93/Kami)**。
- 适配客户端：**[Clash Verge Rev](https://github.com/clash-verge-rev/clash-verge-rev)**。

## 📄 License

[MIT License](./LICENSE)
