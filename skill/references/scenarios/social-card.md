# 场景 · social-card(社交卡片 / 封面)

> 触发:「小红书图文」「小红书卡片」「3:4 卡片」「公众号封面」「微信封面」「21:9」「1:1 封面」「社交卡片」「Swiss 风格卡片」「杂志风」
> 产物:小红书 3:4 图文卡片组 / 公众号 21:9+1:1 封面对 / 文章封面 / 平台缩略图
> embody:平面设计师(电子杂志方向)
> 来源:吸收自 guizang-social-card-skill

## 做什么 / 不做什么

**做**:
- 社交卡片/轮播图组:封面 + 内容页,小红书 3:4
- **公众号封面对**:一张 `21:9` 主封面 + 一张 `1:1` 方封面,**同一个 HTML 里并排合成**以便视觉核对
- 截图密集的产品帖、文章封面、教程轮播、户外/生活笔记、AI/产品更新解读
- Guizang 风 Swiss / editorial 杂志排版

**不做**:
- 完整 deck / 横版 PPT 网站 → 转 `slides.md`
- 长视频 → 转 `motion.md`
- 纯修图(无排版无内容提取需求)→ 不接

## 能力圈(小红书 11 类,诚实边界)

- **端到端强**(文、结构、图故事全包):旅行、职场、推荐(指定子类后)
- **文与结构强,图要 Ed 提供或图库**:游戏、影视、美食(食谱方向)、彩妆(教程方向)、健身、家居、穿搭(精选/capsule 方向)
- **范围外——接活时直说,不硬接**:美食菜品大片摆盘、日常 OOTD 全身、情感梦核/氛围感装饰风、Y2K/千禧辣妹/哥特萝莉/kawaii 装饰美学、纯摄影展示帖
- 路由细节 → `library/social-card/category-cookbook.md`

## 核心原则:表达优先

目标不是把文字塞进海报,而是**把素材转化成一个清晰的视觉论证**。每一页先决定:

- 读者一眼该懂什么?
- 什么证据/截图/图支撑它?
- 哪些字必须大,哪些降级成 caption/meta?
- 什么该删——因为它属于正文不属于图?

## 平台规格与风格

- **规格/尺寸/命名** → `library/social-card/platform-specs.md`
- **Guizang editorial + Swiss 视觉规则** → `library/social-card/style-system.md`
- **主题预设**(电子杂志调色盘 / Swiss accent)→ `library/social-card/theme-presets.md`
- **版式配方**(轮播/卡片/微信页结构)→ `library/social-card/layout-recipes.md`
- **共享组件规范**(字体栈/字号阶/中文标题长度带/Swiss 卡片填充互斥律/图片容器比例类/间距 token/Lucide 图标)→ `library/social-card/components.md`
- **背景系统**(WebGL/水墨/纸感)→ `library/social-card/background-systems.md` + `assets/social-card/magazine-bg-webgl.js`
- **3:4 竖版填充**(避免下方空间没填满)→ `library/social-card/portrait-fill.md`
- 截图处理 → `library/social-card/screenshot-treatment.md` + `assets/social-card/screenshot-backgrounds/`;图片压字 → `library/social-card/image-overlay.md`;地图组件 → `library/social-card/map-component.md`;标题缩写 → `library/social-card/title-shortener.md`;内容规划 → `library/social-card/content-planning.md`

## 模板与验证

- 起手模板:`assets/social-card/template-editorial-card.html` / `assets/social-card/template-swiss-card.html`
- 交付前跑 `node scripts/validate-social-deck.mjs` 结构校验
- 生产流程与 QA → `library/social-card/production-workflow.md` + `library/social-card/qa-checklist.md`

## 三方向门适配

卡片/封面类三方向初稿 = **每方向 1 张真实出图**(不是文字描述风格)。Swiss 与 editorial 是两个现成的差异化大方向,第三方向可走主题色变体或版式反构。

## 验收

- [ ] 尺寸严格符合平台规格(3:4 / 21:9 / 1:1)
- [ ] 封面对同 HTML 并排核对
- [ ] 中文标题长度带合规、最小可读字号达标
- [ ] validate-social-deck.mjs 通过
