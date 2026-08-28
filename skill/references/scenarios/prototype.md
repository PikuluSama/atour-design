# 场景 · prototype(App / Web 高保真原型)

> 触发:「做原型」「交互原型」「app 原型」「iOS mockup」「移动应用」「UI mockup」
> 产物:单文件 HTML 可点击原型,真设备框,Playwright 验证通过
> embody:UX 设计师 + 原型师

## 硬规则(app 原型覆盖通用 placeholder 原则——原型是 demo 现场,静态摆拍没有说服力)

1. **架构默认单文件 inline React**:`file://` 双击就能开,本地图片 base64 内嵌;仅 >1000 行难维护或多 agent 并行写不同屏才拆多文件(拆了必须附 `python3 -m http.server` 启动说明)→ 细节见 `library/app-prototype.md` 与 `library/react-setup.md`
2. **先找真图再设计**:渠道同 direction-advisor Phase 3.5 取图表;取图前过**真图诚实性测试**——「去掉这张图信息是否有损?」无损 = 装饰 = slop,不加
3. **交付形态默认「平铺 4-6 主屏 + 每台可交互」**,不要问 Ed 二选一;每台是独立迷你状态机(tab 可切/按钮可点/能弹 modal),仅 Ed 明确说「只要静态」或「单流程 demo」才偏离
4. 🔴 **iOS 设备框必须用 `assets/ios_frame.jsx`**:禁止手写 Dynamic Island / status bar / home indicator / bezel——自己写 99% 撞位置 bug(岛是固定 124×36)。Android 用 `assets/android_frame.jsx`,桌面场景用 `assets/browser_window.jsx` / `assets/macos_window.jsx`
5. **信息密度分型**:默认克制型(少一层容器/少一个 border/少一个装饰 icon);产品卖点是 AI/数据/上下文感知时走**高密度型**——每屏 ≥3 处**有内容的**差异化信息,装饰 icon 照样忌讳
6. **交付前 Playwright 跑 3 项点击测试**(进详情/关键标注点/tab 切换),`pageerror` 为 0 再交付 → `library/verification.md`
7. **品位锚点**:衬线 display(Newsreader/Source Serif/EB Garamond)+ `-apple-system` body;一个有温度的底色 + 单 accent 贯穿;留一处「值得截图」的 120% 细节签名

## 工作流要点

- Web 原型(非 App):先读 Ed 给的 codebase/设计系统/截图,从 existing context 长出来;没有 → 三方向门
- 交互参数化演示:加 Tweaks 实时调参面板 → `library/tweaks-system.md`
- 多屏切换用状态驱动,不用多文件跳转

## 验收(在基座工程清单之上)

- [ ] Playwright 3 项点击测试通过,console 0 error
- [ ] 单文件双击可开,图片不裂(base64 内嵌)
- [ ] 设备框用 assets 组件,无手写撞位
- [ ] 每屏可交互(非静态摆拍),除非 Ed 明说

## 交接

- 部署/分享:团队若有统一部署流程(如 Cloudflare Pages),按各自约定执行;原型地址建议回写对应需求文档
- 生产级 Web App(需后端/路由/真实数据)→ **让位 `frontend-design`**,本场景止步于原型
