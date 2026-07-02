# DESIGN — Claude Design 소개

Visual identity reference for this composition. All values live on `:root` in `index.html`.

## Palette (warm cream + terracotta, Anthropic tone)

| Token         | Value                  | Use                                  |
| ------------- | ---------------------- | ------------------------------------ |
| `--bg`        | `#EFEAE0`              | Scene background (cream)             |
| `--bg-lite`   | `#F6F2E9`              | Icon fills, light surfaces           |
| `--surface`   | `#FBF8F1`              | Cards, panels                        |
| `--panel`     | `#E7E0D1`              | Secondary panel tone                 |
| `--clay`      | `#CC785C`              | Primary accent (dots, carets, bars)  |
| `--clay-deep` | `#A8543B`              | Accent shadow tone                   |
| `--clay-soft` | `#E3B5A1`              | Underline sweep                      |
| `--ink`       | `#2B2722`              | Primary text                         |
| `--ink-soft`  | `#8A8073`              | Secondary text, labels               |
| `--sage`      | `#5B8C6E`              | Success state (완료)                 |
| `--line`      | `rgba(43,39,34,0.12)`  | Hairlines, borders                   |

## Typography

| Token            | Stack                                | Use                                  |
| ---------------- | ------------------------------------ | ------------------------------------ |
| `--font-serif`   | Gowun Batang, Newsreader, serif      | Korean body/headlines (400 / 700)    |
| `--font-display` | Newsreader, Gowun Batang, serif      | "Claude" wordmark (500, -0.02em)     |
| `--font-mono`    | JetBrains Mono, ui-monospace         | Kickers, labels, DESIGN lockup       |

Sizes: wordmark 152/100px · thesis 116px · scene headlines 58–96px · body 30–42px ·
mono labels 18–24px with 0.3–0.55em letter-spacing.

## Motion language

- Eases: `back.out(1.7)` for dots/buttons, `power3.out` for text entrances,
  `sine.inOut` for breathing/drift, `expo.out` for rules/bars, `steps(1)` for carets.
- Typing is the deterministic counter pattern (`obj.n` tween + `textContent` slice).
- Every scene has continuous mid-scene motion: breathing scale, upward drift, or a
  Ken Burns push (`scale → 1.03`, `ease: "none"`).
- Shader transitions (3): `cinematic-zoom` (hero reveal), `light-leak` (energy shift),
  `cross-warp-morph` (sign-off landing). Everything else is a hard cut.

## Decoratives

- Per-scene vignette: `radial-gradient(125% 125% at 50% 42%, transparent 58%, rgba(43,39,34,0.06) 100%)`,
  outside `.scene-content`.
- Striped image placeholders: `repeating-linear-gradient(135deg, #EAE5DA 0 12px, #E0DACB 12px 24px)`.
