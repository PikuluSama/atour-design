# 项目偏好 · 亚朵星球(atourplanet)

> 🔴 **对内声明**:本仓库含亚朵内部品牌数据(规范/logo),仅供团队成员设计协作使用,严禁外发或放入公开仓库。
> 探测方式:eds-design 检测当前项目根的 `.eds-design/profile.md` 时加载本 profile,叠加在中央默认之上(本文件优先)。

## identity

- 品牌:亚朵星球(atourplanet)
- **规范源**:`brand/brand-spec.md`(Gate 文件,涉品牌产出必读;含「品牌层 vs 数字产品层」判定规则)
- 品牌色(VI 深睡线,不可变更):主 `#002a40` / 辅 `#275e80` `#9dc6c6`;基础线 `#beb8b4` `#487f8c`(无特殊情况不用)
- 集团级场景配色(沃野 `#3b3431` / 白岩 `#ede7e2` / 月晖 / 曦茶):见 `brand/brand-spec.md` §2.4;**集团 vs 星球按物料归属判定**,不混用
- 数字产品层(H5 实测):黑白灰中性 + accent 陶土橙 `#e56a54`;禁用态暖白 `#f2f1ef`;页面底 `#f9f9f9`
- Logo:`brand/logo-white-atour.jpg`(白字锁标/蓝底);● 字符间距比例不可改;浅底黑字版待补
- 字体:VI=方正兰亭黑(中黑/黑/纤黑优先)+ Basis Grotesque(同级中西文字号不得相同);数字层=PingFang SC + 价格数字 DIN Condensed
- 图标库:Heroicons 首选(Tailwind 官方),Font Awesome 备选

## medium(产物规范)

- **原型**:单文件 HTML,桌面默认 1440 档;交互 demo 用真内容(需求里的真实字段/流程),不 Lorem;建议存 `prototypes/{主题}/` 目录
- PPT / 卡片 / 封面等涉品牌产出:先读 `brand/brand-spec.md`
- **无三方向门**:原型不生成多方向供选择,按 `brand/brand-spec.md` 直出单方向——统一品牌规范即唯一方向

## style

- 气质:安静的高级零售感——白底大留白、黑按钮、暖灰阶;品牌区块用深睡蓝 #002a40 压场
- 双层判定:品牌/营销向走 VI 层(蓝+方正兰亭黑+Basis Grotesque);商城/工具向走 H5 实测层(黑白灰+陶土橙 accent+DIN 数字);拿不准默认后者+VI 点缀
- 组件语感:小圆角(4-8px)非胶囊、极轻阴影、少 border 少装饰 icon、禁用态用暖白 #f2f1ef
- OPS 后台层:token 与组件约定见 `brand/brand-spec.md` §8(直出单一标准;旧 Material/AntD/墨绿金语言作废)
- 禁:紫渐变/高饱和多彩/Inter 作 display/冷灰滥用;旧推测色 #4a6b57+#c9a86a 作废
- 功能型产物基准拨盘:VARIANCE 3-4 / MOTION 2 / DENSITY 5-6(重清晰不重炫技)

## ledger

(亚朵专属偏好沉淀于此,格式同中央账本 P-编号制;新增规则请同步给仓库维护者)

- P-001:原型单方向直出,豁免三方向门;一切视觉统一遵循 `brand/brand-spec.md`
