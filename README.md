# 亚朵星球设计工具包(内部)

> **这是什么**:一套让 Claude Code 直出「亚朵星球风格」设计作品的工具包 = **eds-design 设计 skill**(引擎)+ **亚朵品牌规范**(灵魂)。
> 支持:高保真原型(单文件 HTML)、PPT/幻灯片、动画/视频、小红书图文/封面、信息图、落地页、设计评审。
> 🔴 **内部资料**:本仓库含亚朵品牌规范与官方 logo,**仅限团队内部使用,严禁外发、严禁放入公开仓库或公开渠道。**

---

## 一、安装(约 2 分钟)

**前置**:已安装 [Claude Code](https://claude.com/claude-code);`node`(PPT/截图导出需要);`ffmpeg`(仅做视频时需要)。

```bash
# 1. 克隆本仓库到任意位置
git clone <本仓库地址> atour-design
cd atour-design

# 2. 把 skill 链接进 Claude Code 的 skills 目录
mkdir -p ~/.claude/skills
ln -s "$(pwd)/skill" ~/.claude/skills/eds-design

# 3.(首次做 PPT/截图导出时)安装渲染依赖
cd skill && npm install && cd ..
```

## 二、使用

**关键一步:在本仓库目录里启动 Claude Code**(skill 会自动检测当前目录的 `.eds-design/profile.md` 并加载亚朵偏好):

```bash
cd atour-design
claude
```

然后直接说需求即可:

| 想要什么 | 直接说 |
|---|---|
| 高保真原型 | 「做一个售后流程的后台原型」/「做会员商城首页原型」 |
| PPT | 「做一份 10 页的项目汇报 PPT」 |
| 封面/卡片 | 「做公众号封面」/「做小红书 3:4 图文」 |
| 动画/视频 | 「做一个 30 秒的功能演示动画」 |
| 设计评审 | 「评审一下这个页面」 |

产出建议放 `prototypes/{主题}/`,随仓库提交,方便团队互看。

**想在别的项目目录里用?** 把本仓库的 `.eds-design/` 和 `brand/` 两个目录复制到你的项目根目录即可。

## 三、亚朵风格速记(规范详情见 `brand/brand-spec.md`)

1. **先判双层**:品牌/营销向 → VI 层(深睡蓝 `#002a40` + 方正兰亭黑 + Basis Grotesque);商城/工具/后台向 → 数字产品层(黑白灰 + 陶土橙 accent `#e56a54` + DIN 数字)。拿不准 → 后者 + VI 点缀。
2. **单方向直出**:不做多方向风格供选择,品牌规范即唯一方向。
3. **Logo**:用 `brand/logo-white-atour.jpg`,字符间距/比例不可改,只放深底(首选品牌蓝底)。
4. **禁**:紫渐变、高饱和多彩、Inter 作标题、emoji 当图标、Material/AntD 默认色板照搬、冷灰滥用(禁用态用暖白 `#f2f1ef`)。
5. **图标**:Heroicons(Tailwind 官方)。

## 四、维护

- 品牌规范更新(如 VI 换版):修改 `brand/brand-spec.md` 并提交,同步告知团队。
- skill 升级、问题反馈:找仓库维护者。
- 注意:仓库内 `brand/` 资产与 `.eds-design/profile.md` 是配套关系,**不要拆开单独外传**。
- `brand/brand-spec.md` 中引用的部分 `_source/` 原始素材(H5 存档页、VI 手册页面渲染图等)未随仓库分发,需要时向仓库维护者索取。
