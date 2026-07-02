# claude-design-intro

A HyperFrames video composition. Plain HTML + GSAP; rendered to MP4 by the `hyperframes` CLI.

35s · 1920×1080 · 7 scenes — "Claude Design 소개" intro film (warm cream + terracotta,
Korean copy). Converted from a React/Babel Stage-Sprite animation into the HyperFrames
composition format.

## Requirements

- **Node.js 22+** -- [nodejs.org](https://nodejs.org/)
- **FFmpeg** -- `brew install ffmpeg` (macOS) or `sudo apt install ffmpeg` (Debian/Ubuntu) or [ffmpeg.org/download](https://ffmpeg.org/download.html) (Windows)

Verify: `npx hyperframes doctor`

## Preview

```bash
npx hyperframes preview
```

Opens the HyperFrames Studio at `http://localhost:3002` with frame-accurate scrubbing.
(Or open `preview.html` directly in a browser for a quick look.)

## Refine with Claude Code

To polish animations, timing, and pacing:

```bash
npx skills add heygen-com/hyperframes   # install HyperFrames skills (one-time)
npx hyperframes lint                     # verify structure (should pass with zero errors)
npx hyperframes preview                  # open the studio for live feedback
```

Then open in Claude Code and iterate:

- "Make scene 3's typing faster"
- "Tighten the pacing -- scene 4 feels too long"
- "Change the shader on transition 2 to domain-warp"

## Render

```bash
npx hyperframes render index.html -o output.mp4
```

1920x1080 / 30fps by default. Use `--fps 60` or `--resolution 3840x2160` to override.

## Scene map

| Scene | Window       | Content                                        | Transition out    |
| ----- | ------------ | ---------------------------------------------- | ----------------- |
| s1    | 0 – 4.8s     | 브랜드 콜드오픈 (도트 + 링 + Claude 워드마크)  | hard cut          |
| s2    | 4.8 – 9.6s   | 테제 "말하면, 디자인이 됩니다."                | hard cut          |
| s3    | 9.6 – 14.8s  | 프롬프트 타이핑                                | `cinematic-zoom`  |
| s4    | 14.8 – 21.8s | 스트리밍 빌드 히어로 (실시간 슬라이드 생성)    | `light-leak`      |
| s5    | 21.8 – 27.0s | 변형안 3종 (02 선택)                           | hard cut          |
| s6    | 27.0 – 31.6s | 출력물 4종 카드                                | `cross-warp-morph`|
| s7    | 31.6 – 35.0s | 사인오프 "생각을 디자인으로."                  | —                 |
