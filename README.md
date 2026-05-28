# Frontend Design — 统一前端设计 Skill

Claude Code 统一前端设计 Skill，将 20+ 个独立设计 Skill 整合为单一完备的设计-编码系统。

---

## 目录

1. [Skill 简介](#skill-简介)
2. [涵盖内容总览](#涵盖内容总览)
3. [文件结构说明](#文件结构说明)
4. [各模块详细说明](#各模块详细说明)
5. [使用方法](#使用方法)
6. [来源 Skill 清单](#来源-skill-清单)
7. [许可证](#许可证)

---

## Skill 简介

本 Skill 覆盖从设计思考到代码实现的完整链路，适用于：

- 构建网页组件、页面、应用、落地页、仪表盘
- UI 设计评审与优化
- 设计系统搭建与维护
- 用户体验研究与测试
- React/Next.js 性能审计
- GSAP 动画系统实现

触发关键词：UI 设计、UX 流程、设计系统、前端代码、视觉样式、界面评审、重新设计、landing page、dashboard、动画、交互。

---

## 涵盖内容总览

| 模块 | 内容 |
|------|------|
| **1. 需求分流** | 平台、技术栈、页面类型、目标与约束的快速判定 |
| **2. 设计思考** | 内容优先、风格锁定、差异化定位、编码前写作 |
| **3. 内容策略** | 落地页结构、应用/仪表盘布局、文案规则、图像策略 |
| **4. 视觉设计规范** | 排版、色彩、布局、背景与深度 |
| **5. 动效与交互** | CSS 动画模式、Framer Motion、GSAP 完整系统 |
| **6. 组件与按钮** | 原始组件规范、按钮分类体系、变体模式 |
| **7. 设计系统** | Token 生成、色阶、排版尺度、断点、组件架构、开发交接 |
| **8. UX 研究** | 用户画像、旅程地图、可用性测试、研究综合 |
| **9. UI 评审** | 量化评分体系、评审报告结构、UI 模式库、React 性能审计、Web Interface Guidelines |
| **10. 反模式** | 美学/布局/失败模式，明确禁止的设计选择 |
| **11. 最终检查** | 交付前的 10 项必检清单 |
| **12. 输出标准** | 代码交付的完整要求 |

---

## 文件结构说明

本 Skill 除主文件 `SKILL.md` 外，包含大量辅助文件：

```
frontend-design/
├── SKILL.md                          # 主 Skill 文件（核心指南）
├── README.md                         # 本文件
├── LICENSE.txt                       # Apache 2.0 许可证
├── LICENSE-anthropics.txt            # Anthropics 许可证
├── _meta.json                        # Skill 元数据
├── package-ui-audit.json             # UI 审计依赖配置
├── CLAUDE-ui-audit.md                # UI 审计 Claude 专用指南
├── README-ui-audit.md                # UI 审计原始 README
│
├── references/                       # 参考文档（95+ 个 Markdown）
│   ├── ui-audit/                     # 32 个 UI 审计模式与检查清单
│   │   ├── 00-core-framework.md      # 核心审计框架
│   │   ├── 01-anchors.md             # 设计锚点
│   │   ├── 02-information-scaffold.md # 信息架构脚手架
│   │   ├── 10-checklist-new-interfaces.md    # 新界面检查清单
│   │   ├── 11-checklist-fidelity.md          # 保真度检查清单
│   │   ├── 12-checklist-visual-style.md      # 视觉风格检查清单
│   │   ├── 13-checklist-innovation.md        # 创新度检查清单
│   │   ├── 20-patterns-chunking.md           # 内容分块模式
│   │   ├── 21-patterns-progressive-disclosure.md # 渐进披露模式
│   │   ├── 22-patterns-cognitive-load.md     # 认知负荷模式
│   │   ├── 23-patterns-visual-hierarchy.md   # 视觉层级模式
│   │   ├── 24-patterns-social-proof.md       # 社会认同模式
│   │   ├── 25-patterns-feedback.md           # 反馈模式
│   │   ├── 26-patterns-error-handling.md     # 错误处理模式
│   │   ├── 27-patterns-accessibility.md      # 无障碍模式
│   │   ├── 28-patterns-personalization.md    # 个性化模式
│   │   ├── 29-patterns-onboarding.md         # 引导模式
│   │   ├── 30-patterns-information.md        # 信息架构模式
│   │   └── 31-patterns-navigation.md         # 导航模式
│   │
│   ├── design/                       # 18 个设计参考文档
│   │   ├── banner-sizes-and-styles.md
│   │   ├── cip-deliverable-guide.md      # CIP 交付物指南
│   │   ├── cip-design.md
│   │   ├── cip-prompt-engineering.md
│   │   ├── cip-style-guide.md
│   │   ├── design-routing.md
│   │   ├── icon-design.md
│   │   ├── logo-color-psychology.md
│   │   ├── logo-design.md
│   │   ├── logo-prompt-engineering.md
│   │   ├── logo-style-guide.md
│   │   ├── slides-copywriting-formulas.md
│   │   ├── slides-create.md
│   │   ├── slides-html-template.md
│   │   ├── slides-layout-patterns.md
│   │   ├── slides-strategies.md
│   │   ├── slides.md
│   │   └── social-photos-design.md
│   │
│   ├── design-system/                # 8 个设计系统参考文档
│   │   ├── component-specs.md
│   │   ├── component-tokens.md
│   │   ├── primitive-tokens.md
│   │   ├── semantic-tokens.md
│   │   ├── states-and-variants.md
│   │   ├── tailwind-integration.md
│   │   └── token-architecture.md
│   │
│   ├── brand/                        # 12 个品牌参考文档
│   │   ├── approval-checklist.md
│   │   ├── asset-organization.md
│   │   ├── brand-guideline-template.md
│   │   ├── color-palette-management.md
│   │   ├── consistency-checklist.md
│   │   ├── logo-usage-rules.md
│   │   ├── messaging-framework.md
│   │   ├── typography-specifications.md
│   │   ├── update.md
│   │   ├── visual-identity.md
│   │   └── voice-framework.md
│   │
│   ├── slides/                       # 5 个幻灯片参考文档
│   │   ├── copywriting-formulas.md
│   │   ├── create.md
│   │   ├── html-template.md
│   │   ├── layout-patterns.md
│   │   └── slide-strategies.md
│   │
│   └── banner-design/                # 1 个横幅参考文档
│       └── banner-sizes-and-styles.md
│
├── scripts/                          # 可执行脚本（26 个）
│   ├── ui-ux-pro-max/                # UI/UX 搜索与设计系统工具
│   │   ├── core.py
│   │   ├── design_system.py
│   │   └── search.py
│   │
│   ├── design/                       # 创意设计脚本
│   │   ├── cip/
│   │   │   ├── core.py
│   │   │   ├── generate.py
│   │   │   ├── render-html.py
│   │   │   └── search.py
│   │   ├── icon/
│   │   │   └── generate.py
│   │   └── logo/
│   │       ├── core.py
│   │       ├── generate.py
│   │       └── search.py
│   │
│   ├── design-system/                # 设计系统脚本
│   │   ├── embed-tokens.cjs
│   │   ├── fetch-background.py
│   │   ├── generate-slide.py
│   │   ├── generate-tokens.cjs
│   │   ├── html-token-validator.py
│   │   ├── search-slides.py
│   │   ├── slide_search_core.py
│   │   ├── slide-token-validator.py
│   │   └── validate-tokens.cjs
│   │
│   └── brand/                        # 品牌脚本
│       ├── extract-colors.cjs
│       ├── inject-brand-context.cjs
│       ├── sync-brand-to-tokens.cjs
│       └── validate-asset.cjs
│
├── data/                             # 数据文件（58 个 CSV）
│   ├── ui-ux-pro-max/                # UI/UX 数据表
│   │   ├── colors.csv
│   │   ├── typography.csv
│   │   ├── icons.csv
│   │   ├── landing.csv
│   │   ├── app-interface.csv
│   │   ├── charts.csv
│   │   ├── google-fonts.csv
│   │   ├── products.csv
│   │   ├── react-performance.csv
│   │   ├── styles.csv
│   │   ├── ui-reasoning.csv
│   │   ├── ux-guidelines.csv
│   │   ├── design.csv
│   │   ├── draft.csv
│   │   ├── _sync_all.py
│   │   └── stacks/                   # 技术栈数据（16 个框架）
│   │       ├── angular.csv
│   │       ├── astro.csv
│   │       ├── flutter.csv
│   │       ├── html-tailwind.csv
│   │       ├── jetpack-compose.csv
│   │       ├── laravel.csv
│   │       ├── nextjs.csv
│   │       ├── nuxt-ui.csv
│   │       ├── nuxtjs.csv
│   │       ├── react-native.csv
│   │       ├── react.csv
│   │       ├── shadcn.csv
│   │       ├── svelte.csv
│   │       ├── swiftui.csv
│   │       ├── threejs.csv
│   │       └── vue.csv
│   │
│   ├── design/                       # 设计数据
│   │   ├── cip/
│   │   │   ├── deliverables.csv
│   │   │   ├── industries.csv
│   │   │   ├── mockup-contexts.csv
│   │   │   └── styles.csv
│   │   ├── icon/
│   │   │   └── styles.csv
│   │   └── logo/
│   │       ├── colors.csv
│   │       ├── industries.csv
│   │       └── styles.csv
│   │
│   └── design-system/                # 设计系统数据
│       ├── slide-backgrounds.csv
│       ├── slide-charts.csv
│       ├── slide-color-logic.csv
│       ├── slide-copy.csv
│       ├── slide-layout-logic.csv
│       ├── slide-layouts.csv
│       ├── slide-strategies.csv
│       └── slide-typography.csv
│
├── templates/                        # 模板文件
│   ├── brand/
│   │   └── brand-guidelines-starter.md
│   └── design-system/
│       └── design-tokens-starter.json
│
└── canvas-fonts/                     # Canvas 渲染字体（30+ 个）
    └── ui-styling/
        ├── ArsenalSC-Regular.ttf
        ├── BigShoulders-Bold.ttf
        ├── BricolageGrotesque-Bold.ttf
        ├── CrimsonPro-Bold.ttf
        ├── CrimsonPro-Italic.ttf
        ├── DMMono-Regular.ttf
        ├── EricaOne-Regular.ttf
        ├── GeistMono-Bold.ttf
        ├── GeistMono-Regular.ttf
        ├── Gloock-Regular.ttf
        ├── IBMPlexMono-Bold.ttf
        ├── IBMPlexMono-Regular.ttf
        ├── IBMPlexSerif-Bold.ttf
        ├── IBMPlexSerif-Italic.ttf
        ├── InstrumentSans-Bold.ttf
        ├── InstrumentSans-Italic.ttf
        ├── InstrumentSerif-Italic.ttf
        ├── Italiana-Regular.ttf
        ├── JetBrainsMono-Bold.ttf
        ├── JetBrainsMono-Regular.ttf
        ├── Jura-Light.ttf
        ├── Jura-Medium.ttf
        ├── LibreBaskerville-Regular.ttf
        ├── Lora-Bold.ttf
        ├── Lora-BoldItalic.ttf
        ├── Lora-Italic.ttf
        ├── NationalPark-Bold.ttf
        ├── NationalPark-Regular.ttf
        ├── NothingYouCouldDo-Regular.ttf
        ├── Outfit-Bold.ttf
        ├── Outfit-Regular.ttf
        ├── PixelifySans-Medium.ttf
        ├── PoiretOne-Regular.ttf
        ├── RedHatMono-Bold.ttf
        ├── RedHatMono-Regular.ttf
        ├── Silkscreen-Regular.ttf
        ├── SmoochSans-Medium.ttf
        ├── Tektur-Medium.ttf
        ├── Tektur-Regular.ttf
        ├── WorkSans-Bold.ttf
        ├── WorkSans-BoldItalic.ttf
        ├── WorkSans-Italic.ttf
        ├── WorkSans-Regular.ttf
        ├── YoungSerif-Regular.ttf
        └── ...（含 OFL 许可证文件）
```

---

## 各模块详细说明

### 1. 需求分流（Triage）

编码前先明确五个问题：目标平台、技术栈、页面类型、目标与约束、已有资源。若用户要求"全部都要"（设计 + UX + 代码 + 设计系统），按此顺序交付：**UX 流程 → 设计系统 → UI 概念 → 实现方案**。

### 2. 设计思考（Design Thinking）

**内容优先**：先确定页面类型，再选择视觉方向。工具页、搜索页、信任页应更清晰冷静；推广页、文化页可以更大胆张扬。

**风格锁定**：从以下极端风格中选择一种并严格执行：
- 极致极简 / 极繁混沌 / 复古未来 / 有机自然 / 奢华精致 /  playful 玩具风 / 编辑杂志风 / 粗野主义 / 装饰几何 / 柔和 pastel / 工业实用

**编码前写作**：视觉论点（一句描述情绪、材质、能量）、内容计划（hero → support → detail → CTA）、交互论点（2-3 个改变页面感受的动效想法）。

### 3. 内容策略（Content Strategy）

**落地页默认结构**：
1. Hero：品牌/产品、承诺、CTA、一个主导视觉
2. Support：一个具体功能、优惠或证明点
3. Detail：氛围、工作流、产品深度或故事
4. 最终 CTA：转化、开始、访问或联系

**Hero 规则**：全出血图片或主导视觉平面；品牌第一、标题第二、正文第三、CTA 第四；禁用 hero 卡片、统计条、logo 云、药丸堆、悬浮仪表盘。

**仪表盘默认风格**：Linear 式克制——平静的表面层级、强排版与间距、少色彩、密集但可读、最小装饰、仅在卡片是交互对象时才用卡片。

**文案规则**：用产品语言，不用设计评论；让标题承载含义；支持文案通常应为一句短句；删减 30% 后若页面更好，继续删。

### 4. 视觉设计规范

**排版**：禁用通用字体（Inter、Roboto、Arial、系统字体）。正文基线 15-18px；标题比例 H1=body×2.2-2.6、H2=body×1.6-1.9、H3=body×1.3-1.5；行高正文 1.45-1.6、标题 1.15-1.3；字间距标题 -1% 至 -3%、正文 0% 至 +1%。

**色彩**：1 个主色 + 1 个辅色 + 1 个强调色 + 1 个中性基色。文本对比度 ≥4.5:1，交互元素 ≥3:1。强调色使用面积 ≤10%，仅允许 1 个饱和色。

**布局**：单一间距基准（8px 或 10px）。视觉权重分配：主区域 40-55%、次区域 25-35%、第三区域 ≤20%。每视图最多两条对齐轴。

### 5. 动效与交互

**CSS 动画模式**：fadeIn、pulse、spin、卡片悬停 lift、涟漪效果、滑动删除、页面过渡。

**GSAP 动画系统**：
- 核心方法：`gsap.to/from/fromTo/set`
- 时间轴：序列控制、标签、嵌套、播放控制
- ScrollTrigger：滚动驱动动画、pin、batch、refresh
- 响应式：`gsap.matchMedia()` 适配断线与减弱动效
- React/Vue/Svelte 集成：`useGSAP` hook、`gsap.context()` 作用域管理
- 性能：仅动画 `transform` 和 `opacity`、使用 `gsap.quickTo()`、虚拟化长列表
- 完整插件速查：Flip、SplitText、DrawSVG、MorphSVG、MotionPath、Observer、CustomEase 等

### 6. 组件与按钮

**原始组件**：必须使用可访问组件基元（Base UI、React Aria、Radix）。图标按钮必须加 `aria-label`。破坏性操作必须用 `AlertDialog`。

**按钮分类体系**：
| 类型 | 用途 | 视觉处理 |
|------|------|----------|
| 异步生成 | AI 操作、长时间任务 | 清晰状态切换、闪光图标、微光 |
| 主 CTA | Hero 动作、引导 | 更强轮廓、箭头动效、光标响应强调 |
| 次 CTA | 支持动作 | 更轻动效、更干净结构 |
| 文本按钮 | 编辑、未来感、实验性 | 文本揭示、光标动效、克制的发光强调 |
| 隐藏 CTA | 安静默认、悬停奖励 | 悬停时受控激活 |
| 图标按钮 | 社交链接、工具控制 | 充足点击区域、清晰悬停反馈 |

### 7. 设计系统

**Token 生成**：从品牌色生成完整设计 token 系统——颜色（主/次/中性/语义/表面）、排版（字体族/字号/字重/行高）、间距（8pt 网格 0-64）、边框（圆角/宽度）、阴影（none 至 2xl）、动画（时长/缓动）、断点（xs 至 2xl）。

**色阶**：50-900 共 10 级，基于原始色的亮度与饱和度系统推导。

**排版尺度**：1.25x 比例——xs(10px)、sm(13px)、base(16px)、lg(20px)、xl(25px)、2xl(31px)、3xl(39px)、4xl(49px)、5xl(61px)。

**组件架构**：Atoms → Molecules → Organisms → Templates。

### 8. UX 研究

**用户画像生成**：需要 JSON 格式用户数据（user_id、age、usage_frequency、features_used、primary_device、usage_context、tech_proficiency、pain_points）。输出：原型、人口统计、目标与需求、痛点（含频率计数）、设计启示。

**旅程地图**：B2B SaaS 典型阶段：认知 → 评估 → 引导 → 采用 → 倡导。每阶段记录：行动、触点、情绪(1-5)、痛点、机会。机会优先级分数 = 频率 × 严重程度 × 可解决性。

**可用性测试**：将模糊目标转化为可测试问题。成功率目标 >80%、任务时间 <2x 预期、错误率 <15%、满意度 >4/5。

### 9. UI 评审

**量化评分（0-10 分）**：
| 维度 | 权重 | 阈值 |
|------|------|------|
| 排版 | 20% | ≥8：层级瞬间可读 |
| 色彩 | 20% | ≥8：主次与强调明确 |
| 布局 | 20% | ≥8：视线 1-2 秒内解决 |
| 动效 | 15% | ≥8：动效提升理解 |
| UX | 15% | ≥8：意图明确、操作 effortless |
| 背景 | 10% | ≥7：深度支持层级 |
| 跨维度和谐 | 强制 | ≥8：所有维度强化同一层级 |

**React/Next.js 性能审计清单**：
- 数据获取：消灭瀑布流（用 Promise.all）、Server Components 取数据、Streaming Suspense
- 渲染：最小化 Client Components、提升 JSX、useMemo/useCallback 不 premature
- 包体积：动态导入大库、tree-shake、@next/bundle-analyzer
- 图片：Next.js `<Image>`、WebP/AVIF、正确 sizes 与 priority
- CSS：CSS Modules 或 Tailwind、生产 purge
- 表单：autocomplete、客户端验证、内联错误
- 无障碍：aria-label、focus 状态、对比度 ≥4.5:1

### 10. 反模式

**美学反模式**：禁用通用字体、紫色渐变、可预测布局、AI 俗套选择（Space Grotesk 等）、未请求的渐变、紫色/多色渐变、发光效果作为主要 affordance、未请求的字间距修改。

**布局反模式**：默认不用卡片、不用 hero 卡片、不用分屏 hero（除非文本在平静统一的一侧）、每区域不超过一个主导想法、标题不压倒品牌、无填充文案、无正当理由不超过两种字体、无强系统不超过一种强调色。

### 11. 最终检查清单

交付前验证：
- 品牌/产品在首屏是否 unmistakable？
- 是否有一个强视觉锚点？
- 仅扫描标题能否理解页面？
- 每个区域是否只有一个职责？
- 卡片是否真正必要？
- 动效是否改善层级或氛围？
- 移除所有装饰阴影后设计是否仍显高级？
- 删除 30% 文案是否改善页面？
- 所有交互元素是否满足对比度要求？
- 是否尊重 `prefers-reduced-motion`？

---

## 使用方法

### 安装到 Claude Code

将本仓库克隆到 Claude Code 的 skills 目录：

```bash
git clone https://github.com/sunyifeisb-art/frontend-design-skill.git \
  ~/.claude/skills/frontend-design
```

或手动复制 `SKILL.md` 及所有辅助文件到 `~/.claude/skills/frontend-design/`。

### 使用方式

在 Claude Code 对话中，Claude 会自动根据请求内容触发本 Skill。也可通过以下方式显式调用：

- "帮我设计一个 landing page"
- "评审这个 UI 设计"
- "创建设计系统 token"
- "优化这个 React 组件的性能"
- "给这个页面加 GSAP 动画"
- "做用户画像分析"

### 引用辅助文件

需要深入参考时，Claude 会读取 `references/`、`scripts/`、`data/` 中的对应文件。例如：
- UI 审计时读取 `references/ui-audit/00-core-framework.md`
- 设计系统时读取 `references/design-system/token-architecture.md`
- 品牌设计时读取 `references/brand/visual-identity.md`

---

## 来源 Skill 清单

本 Skill 整合自以下 20+ 个独立 Skill：

| 来源 Skill | 贡献内容 |
|------------|----------|
| `frontend-design` (v1) | 核心设计指南、GSAP 系统 |
| `frontend-design-3-0.1.0` | 高质感前端接口、设计思考 |
| `frontend-skill` | 视觉强落地页、图像主导层级 |
| `human-optimized-frontend` | 量化评估体系、动效规范 |
| `interaction-design` | 微交互、过渡、反馈模式 |
| `ui-design-system` | 设计 token、组件文档 |
| `ui-skills` | 界面约束、最佳实践 |
| `ui-audit` | 32 个审计模式与检查清单 |
| `ui-ux-pro-max` | 脚本、数据表、技术栈 |
| `ux-researcher-designer` | UX 研究流程、画像生成 |
| `web-design-guidelines` | Web Interface Guidelines 评审 |
| `pinak-frontend-guru` | React/Next.js 性能审计 |
| `frontend-design-anthropics` | 官方前端设计规范 |
| `gsap-core` | GSAP 核心 API |
| `gsap-timeline` | 时间轴序列 |
| `gsap-scrolltrigger` | 滚动驱动动画 |
| `gsap-react` | React 集成 |
| `gsap-plugins` | 插件系统 |
| `gsap-utils` | 工具函数 |
| `gsap-frameworks` | 框架集成 |
| `gsap-performance` | 性能优化 |
| `design` | 幻灯片、横幅、logo、icon、CIP 设计 |
| `design-system` | Token 架构、Tailwind 集成 |
| `brand` | 品牌指南、视觉识别 |
| `slides` | 幻灯片布局与模板 |
| `banner-design` | 横幅尺寸与风格 |
| `ui-styling` | Canvas 字体资源 |

---

## 许可证

Apache License 2.0

部分辅助文件来自各自原始 Skill，保留其原始许可证（见 `LICENSE-anthropics.txt` 及各字体 OFL 许可证文件）。
