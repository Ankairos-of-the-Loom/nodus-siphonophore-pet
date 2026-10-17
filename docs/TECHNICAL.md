# Technical specification

## Atlas

- Format: transparent PNG
- Dimensions: 1536 × 2288 pixels
- Grid: 8 columns × 11 rows
- Cell size: 192 × 208 pixels
- Sprite version: v2

### Rows

| Row | State | Used frames |
|---:|---|---:|
| 0 | Idle | 6 |
| 1 | Travel right | 8 |
| 2 | Travel left | 8 |
| 3 | Greeting / wave | 4 |
| 4 | Jump / levitation | 5 |
| 5 | Failure / recovery | 8 |
| 6 | Waiting / needs input | 6 |
| 7 | Active work | 6 |
| 8 | Review / ready | 6 |
| 9 | Look 000° through 157.5° | 8 |
| 10 | Look 180° through 337.5° | 8 |

Unused cells in rows 0 and 3–8 are fully transparent.

## Direction order

The final two rows contain sixteen clockwise directions in 22.5-degree increments:

`000`, `022.5`, `045`, `067.5`, `090`, `112.5`, `135`, `157.5`, `180`, `202.5`, `225`, `247.5`, `270`, `292.5`, `315`, `337.5`.

Screen-left and screen-right are viewer-relative.

## Validation

The exact published PNG passed:

- ChatGPT pet structural validation (`valid: true`).
- Full atlas geometry and transparency validation.
- Required-frame review for all nine behavior rows.
- Sixteen-direction semantic review.
- Registration and continuity measurement.
- Motion-quality checks, including a 22-pixel airborne lift and exact return to the idle baseline.

Machine-readable reports are preserved in [`qa/`](../qa/).

SHA-256 of the published atlas:

`4fadb055a1e96d06b3b4468eb5eeed704a6c37400592975fce3ee00d5761baa9`

