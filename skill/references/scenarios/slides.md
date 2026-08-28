# 场景 · slides(幻灯片 / PPT / deck)

> 触发:「PPT」「幻灯片」「deck」「演讲稿」「做个演示」
> 产物:HTML deck(浏览器演讲)+ 自动 PDF + 按需可编辑 PPTX
> embody:幻灯片设计师

## 固定交付链(开工不问格式)

1. **HTML deck**:每页独立 `<section>`(1920×1080)套 `assets/deck_index.html` 概览墙外壳
2. 完成后**自动**出 PDF:`node scripts/export_deck_pdf.mjs`(不问直接给)
3. **询问**才出可编辑 PPTX:`scripts/export_deck_pptx.mjs`(best-effort 衍生物,**绝不**为迁就 html2pptx 约束而降级 HTML 设计,转不出就如实说损失了什么)→ `library/editable-pptx.md`

## 硬规则

- 🔴 **≥5 页必须先做 2 页 showcase 定 grammar 再批量**——跳过 = 方向错返工 N 次而非 2 次
- **绝不写竖向平铺长页冒充 deck**——PPT 场景必走 deck 模板
- **单页内容绝不自带页码/进度标记**——页码由 deck 外壳统一承载(实测出过「02/03」+「6/16」双页码打架)
- 走三方向门时:三版各出 **2 页代表页**(兼作 showcase),选定方向后再批量其余页;三版只换视觉风格,deck 骨架统一
- 截图按**单页** 1920×1080 截

## 深度参考

- 架构规则、概览墙、交付格式决策树 → `library/slide-decks.md`
- PPTX 导出细节与保真边界 → `library/editable-pptx.md`
- 排版音阶(1.5 纯五度适合 slides)→ `foundation/typography.md`
- 缩略图生成:`node scripts/gen_deck_thumbs.mjs`

## 验收

- [ ] 每页 1920×1080,deck_index.html 概览墙可浏览
- [ ] PDF 已自动产出
- [ ] 页码无重复(外壳统一)
- [ ] 观众距离 = 投屏(10m):字号够大、每页信息量克制(form 五问第 2 问)

## 交接

- 导出 PPTX 后 Ed 要自己改 → 确认真实文本框保留(非图片)
- 演讲动画化(把 deck 变成视频)→ 转 `motion.md` 场景
