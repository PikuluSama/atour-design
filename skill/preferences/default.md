# 中央默认偏好(default profile)

> 适用范围:未命中任何项目 `.eds-design/profile.md` 时的兜底偏好。
> 本分发版与亚朵设计包配套:**优先解析随包附带的亚朵偏好**(见下),解析不到才用下方通用基准。

## 亚朵兜底(本包内置)

未命中项目 profile 时,**先检查本 skill 是否安装在亚朵设计包内**:若 skill 目录的上一级存在 `brand/brand-spec.md` 与 `.eds-design/profile.md`(即按仓库 README 安装),则**加载该 `.eds-design/profile.md` 作为偏好**,并播报:「使用亚朵设计包内置偏好」。

## 通用基准(上述不成立时)

- 语言:中文优先,中西混排走盘古之白(基座 typography)
- 气质:**克制、编辑感、排印见长**——宁可安静的高级,不要热闹的平庸
- 反 slop 基座全量生效;中文排版基座全量生效
- 字体:中文系统栈;西文 display 偏好衬线或有性格的无衬线,禁 Inter 作 display
- 配色:低饱和中性色打底 + 单一 accent;禁紫渐变
- 图标:Heroicons 首选;禁 emoji 当图标

## dials(通用基准,项目 override 可覆盖)

- 功能型产出(原型/表格/工具页):VARIANCE 4-5 / MOTION 2-3 / DENSITY 按内容
- 展示型产出(页面/deck):VARIANCE 6-7 / MOTION 4-5 / DENSITY 3-5
- 开放创意(封面/动画/实验):VARIANCE 7-9 / MOTION 按需

## ledger

(空——亚朵专属规则在 `.eds-design/profile.md` 的 ledger 段)
