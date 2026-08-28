# 场景 · motion(动画 / 视频 / 宣传片)

> 触发:「动画」「做成视频」「导出 MP4/GIF」「宣传片」「launch film」「带解说的视频」「科普动画」
> 产物:时间轴动画 HTML → MP4(默认带 BGM+SFX)/ GIF
> embody:动画师 + 导演

## 开工前硬门

- 🔴 **Gate 文件**:`direction-approved.md` 必备;≥20s 动画必须有 `导演稿.md`(最低要求 = `library/storyboard-basics.md` §5 轻量分镜卡:八字段/镜,含 [CAMERA] 列与验收帧号);launch film 级(「Apple 级」「超级碗品质」)升级为万字 director's notes → `library/launch-film-director-notes.md`
- 🔴 **渲染前 hook**:`scripts/design-gate-hook.sh` 检查 gate 文件,缺则 block(Ed 明说跳过用 `SKIP_DESIGN_GATE=1`)
- **铁律 3 条**(写代码前必答):① hero element 是什么?② 它跨段怎么 morph?③ 任意一帧画面有运动吗?答不上不要写代码

## 分阶段管线

**分镜先行**:每一镜先是一张会动的封面;镜头级运动(zoom/pan/转场)必读 `library/camera-language.md`;分镜基础 → `library/storyboard-basics.md`

**实现**:
- **新动画项目默认 HyperFrames 后端**:`npm run check`(五门审计)→ `npx hyperframes render --fps 60` → `scripts/verify-video.sh` 产物硬校验。选型边界与老 demo 适配 → `library/hyperframes-backend.md`;GSAP 实现配方 → `library/gsap-recipes.md`
- 弱 runtime/单文件交付/纯交互演示 → 自研管线:`scripts/render-video.js` 录 25fps 纯画面(只是中间产物);需要真 60fps/确定性 → `scripts/render-video-seek.js --fps=60`
- 动效避坑 → `library/animation-pitfalls.md`(动手前必读);最佳实践 → `library/animation-best-practices.md`;电影感模式 → `library/cinematic-patterns.md`;场景模板 → `library/scene-templates.md`
- **UI 界面是主角时**(产品动画/功能演示/商单)→ 单一入口 `library/ui-demo-animation.md`(截图运镜 vs HTML 重建决策树 + UI 展示八式 + `assets/cursor.jsx` 光标组件)

**音频(默认交付 = 带音频的 MP4,无声版本 = 半成品)**:
- `scripts/convert-formats.sh` 派生 60fps MP4 + palette 优化 GIF
- `scripts/add-music.sh` 加 BGM(6 首场景化配乐:tech/ad/educational/tutorial + alt)
- SFX 按 `library/audio-design-rules.md` 设计 cue 清单,用 `assets/sfx/` 预制资源,按配方选密度(发布 hero ≈ 6个/10s,工具演示 ≈ 0-2个/10s)→ `library/sfx-library.md` + `scripts/sfx-cues.sh`
- **BGM + SFX 双轨必须同时做**——只做 BGM 是 ⅓ 完成度;频段隔离见 audio-design-rules 的 ffmpeg 模板
- 交付前 `ffprobe -select_streams a` 确认有 audio stream
- 跳过音频的条件:Ed 明确说「不要音频/纯画面/我自己配音」

**带解说长视频(≥1分钟,5-20分钟科普)**:**不要先做动画再配音**——走解说驱动流程 `library/voiceover-pipeline.md`:写解说稿(`## scene-id` 分段 + `[[cue:xx]]`)→ `scripts/narrate-pipeline.mjs`(TTS)→ timeline.json → `assets/narration_stage.jsx`(NarrationStage + Subtitles)→ `scripts/render-narration.sh` 自动录音混音

**终渲后(可选)**:AI 看片评审(云能力,自备 key + 显式确认,见 SECURITY.md)→ `library/ai-video-review.md`;无 key 用 `scripts/verify-video.sh` 截帧人工看

## 验收

- [ ] gate 文件齐(direction-approved + 导演稿/分镜卡)
- [ ] MP4 有 audio stream(BGM+SFX 双轨)
- [ ] verify-video.sh 通过(无黑帧/死段)
- [ ] 三方向门走的是「方向板」形态(关键帧截图 + 色板 + 气质定位),不是三支成片
