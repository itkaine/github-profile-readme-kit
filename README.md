<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:7F5AF0,50:E45FB0,100:2CB67D&height=180&section=header&text=Profile%20README%20Kit&fontSize=48&fontColor=ffffff&fontAlignY=38&desc=Copy%20%C2%B7%20Replace%20%C2%B7%20Shine&descAlignY=60&descSize=18&animation=fadeIn" alt="Profile README Kit" width="100%" />
</p>

<p align="center">
  Ready-to-use GitHub profile README templates, plus a cheat sheet for every widget they use.<br/>
  No build step, no workflow, no API keys. Copy a template, replace the placeholders, done.
</p>

<p align="center">
  <img src="https://img.shields.io/github/stars/itkaine/github-profile-readme-kit?style=for-the-badge&color=E45FB0" alt="Stars" />
  <img src="https://img.shields.io/github/license/itkaine/github-profile-readme-kit?style=for-the-badge&color=7F5AF0" alt="License" />
  <img src="https://img.shields.io/badge/templates-3-2CB67D?style=for-the-badge" alt="Templates" />
</p>

---

## Quick start

1. Create a public repo named exactly like your username (`YOUR_USERNAME/YOUR_USERNAME`). GitHub shows its `README.md` on your profile.
2. Pick a template from the table below and copy its contents into that `README.md`.
3. Search for `YOUR_` and replace every placeholder.
4. Commit. Your profile updates right away.

## Templates

| Template | Style | Best for |
|---|---|---|
| [Gradient Wave](templates/gradient-wave.md) | Animated wave banner, typing line, badges, stats and streak cards | Frontend and design-minded devs who want a polished look |
| [Minimal](templates/minimal.md) | Short intro, small flat badges, one icon row | People who want something clean and quick to read |
| [Terminal](templates/terminal.md) | Monospace typing line, shell-style "about me", dark cards | Backend, DevOps and CLI fans |

The live example of **Gradient Wave** is [github.com/itkaine](https://github.com/itkaine).

## Widget cheat sheet

Every template is built from these free services. All of them render an SVG from the URL, so you customize them by editing query parameters.

### Header and footer banner: [capsule-render](https://github.com/kyechan99/capsule-render)

```
https://capsule-render.vercel.app/api?type=waving&color=0:7F5AF0,100:2CB67D&height=200&section=header&text=Hello&fontColor=ffffff&animation=fadeIn
```

| Param | What it does | Examples |
|---|---|---|
| `type` | Shape | `waving`, `wave`, `rect`, `slice`, `egg`, `shark`, `soft`, `cylinder`, `venom`, `transparent` |
| `color` | Fill. Use gradient stops `0:HEX,50:HEX,100:HEX`, or `gradient` / `random` for presets | `0:7F5AF0,100:2CB67D` |
| `section` | `header` (shape at the top) or `footer` (shape flipped) | `footer` |
| `text`, `desc` | Title and subtitle, URL-encoded | `Hi%2C%20I'm%20Kai` |
| `fontSize`, `descSize`, `fontColor` | Text styling | `56`, `18`, `ffffff` |
| `fontAlignY`, `descAlignY` | Vertical position in % | `36`, `58` |
| `animation` | Entry effect | `fadeIn`, `scaleIn`, `blink`, `twinkling` |

### Typing line: [readme-typing-svg](https://github.com/DenverCoder1/readme-typing-svg)

| Param | What it does |
|---|---|
| `lines` | Lines to type, separated by `;` and URL-encoded (`+` for spaces) |
| `font`, `size`, `weight`, `color` | Any Google Font name, px size, weight, hex color without `#` |
| `duration`, `pause` | Typing time per line and pause between lines, in ms |
| `center`, `vCenter`, `width`, `height` | Layout. Raise `width` if long lines get clipped |
| `multiline`, `repeat` | Keep previous lines visible, loop forever or not |

### Badges: [shields.io](https://shields.io)

```
https://img.shields.io/badge/<Label>-<HEX>?style=for-the-badge&logo=<slug>&logoColor=white
```

- `style`: `flat`, `flat-square`, `for-the-badge`, `plastic`, `social`
- `logo`: any slug from [simple-icons](https://simpleicons.org) (`linkedin`, `x`, `facebook`, `buymeacoffee`, …)
- A `-` inside the label must be written as `--`, and a space as `%20` or `_`

### Tech stack icons: [skillicons.dev](https://skillicons.dev)

```
https://skillicons.dev/icons?i=html,css,js,ts,react,vue&perline=8&theme=dark
```

- `i`: comma-separated icon IDs (full list on the site, e.g. `ps` = Photoshop, `ai` = Illustrator)
- `perline`: icons per row (1–50)
- `theme`: `dark` or `light`
- Tip: split long stacks into several rows grouped by topic (frontend, tools, design)

### Profile views: [komarev](https://github.com/antonkomarev/github-profile-views-counter)

```
https://komarev.com/ghpvc/?username=YOUR_USERNAME&style=for-the-badge&color=7F5AF0&label=PROFILE+VIEWS
```

The count is stored per `username` value in the URL, not per GitHub account. If you rename your account, keep the old value in the URL to keep your count.

### Stats cards: [github-profile-summary-cards](https://github.com/vn7n24fzkq/github-profile-summary-cards)

```
https://github-profile-summary-cards.vercel.app/api/cards/<card>?username=YOUR_USERNAME&theme=<theme>
```

- `card`: `profile-details`, `stats`, `most-commit-language`, `repos-per-language`, `productive-time` (add `&utcOffset=7` for your timezone)
- `theme`: `default`, `github`, `github_dark`, `tokyonight`, `dracula`, `nord_dark`, `radical`, …

### Streak card: [streak-stats](https://github.com/DenverCoder1/github-readme-streak-stats)

```
https://streak-stats.demolab.com?user=YOUR_USERNAME&theme=tokyonight&hide_border=true
```

Override any color with `background`, `ring`, `fire`, `currStreakLabel`, `sideNums`, `dates` (hex without `#`).

## Common pitfalls

| Problem | Cause | Fix |
|---|---|---|
| Stats card shows an error or a blank image | The shared public instance of `github-readme-stats` is often rate-limited (HTTP 503) | Use `github-profile-summary-cards` like these templates, or self-host `github-readme-stats` on your own Vercel account |
| View count reset to 0 | The counter URL uses a different `username` value | Put back the value you used before |
| README gets overwritten every day | An old GitHub Action (quote generator, WakaTime, …) still writes to `README.md` | Delete or disable the workflow in `.github/workflows/` |
| Images look wrong on light mode | Card themes are dark | Use a neutral theme, or wrap images in `<picture>` with `prefers-color-scheme` sources |
| Long typing line is cut off | `width` too small | Increase `width` in the typing SVG URL |

## Contributing

New templates are welcome. Add one file to `templates/`, use only `YOUR_*` placeholders for personal data, check that every image URL returns HTTP 200, and add a row to the table above.

## License

[MIT](LICENSE)
