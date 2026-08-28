# 场景 · web(落地页 / 展示页 / 营销页)

> 触发:「落地页」「展示页」「营销页」「官网首页」「做个网页」
> 产物:HTML 页面(设计导向,非生产级应用)
> embody:网页设计师

## 边界(先判断再动手)

- ✅ 本场景管:**设计导向**的落地页、展示页、营销页、活动页、作品集页
- ❌ 让位 `frontend-design`:生产级 Web App、需后端/路由/鉴权/真实数据的系统、SEO 关键站
- 判断口诀:**「这是给人看的一页,还是给人用的系统?」** 看的 → 本场景;用的 → frontend-design

## 工作要点

1. **从 existing context 出发**:有品牌走资产协议(brand-spec.md);有参考站先拆解其设计语言再迁移
2. **三方向门照走**:网页类三方向 = 每方向 1 个完整 HTML + 截图;三版布局骨架必须互异
3. **首屏即立场**:hero 区在一屏内说清「这是什么 + 为什么值得留」;不做居中 Hero + 三等分卡片的 AI 默认套路(anti-slop)
4. **内容与文案**:真实内容不 Lorem;文案去 AI 味(空洞营销词禁用);中文页面走中文排版规范
5. **响应式**:桌面 1440 为主设计,移动端 390 校验;`clamp()` 流式字号
6. **风格取材**:40 种风格库(网页 20 种)→ `library/design-styles.md`;设计语境挖掘 → `library/design-context.md`

## 深度参考

- 品位锚点与兜底 → `library/design-context.md`
- 风格库全表(还原度/温度/HTML 实现/开源字体)→ `library/design-styles.md`
- 反 slop 清单 → `foundation/anti-slop.md` + `library/content-guidelines.md`
- Apple 画廊式展示页范式 → `library/apple-gallery-showcase.md`
- React 工程化(需要组件化时)→ `library/react-setup.md`

## 验收

- [ ] 首屏信息完整(是什么+为什么留下)
- [ ] 1440 / 390 两档截图无破版
- [ ] 无 anti-slop 禁令命中(除非品牌 spec 破例)
- [ ] 基座工程清单通过(对比度/焦点/交互态)

## 交接

- 页面要上线 → Ed 自行部署或走其部署流程;本场景不部署
- 做完了要评审 → `playbooks/review.md`
