[English](README.md) | [Français](README.fr.md)

# github-readme-weather

Free weather badges for a GitHub README, a profile, a forum signature or any page that can show an image. Each badge is a small SVG served by [weatheo.com](https://weatheo.com) that shows the current weather of one place.

The examples below use Paris and London. The paths are examples: check the exact path of your city on weatheo.com (see "Find your city").

Line badge, light and dark:

[![Weather in Paris](https://weatheo.com/badge/fr/ile-de-france/paris.svg?lang=en)](https://weatheo.com/en/fr/ile-de-france/paris)
[![Weather in Paris, dark theme](https://weatheo.com/badge/fr/ile-de-france/paris.svg?lang=en&theme=dark)](https://weatheo.com/en/fr/ile-de-france/paris)

Card badge (495x120), light and dark:

[![Weather in London](https://weatheo.com/badge/gb/london-city-of/london.svg?style=card&lang=en)](https://weatheo.com/en/gb/london-city-of/london)
[![Weather in London, dark theme](https://weatheo.com/badge/gb/london-city-of/london.svg?style=card&theme=dark&lang=en)](https://weatheo.com/en/gb/london-city-of/london)

## Find your city

1. Open [weatheo.com](https://weatheo.com) and search for your city.
2. On the city page, copy the part of the address after the language. For `https://weatheo.com/en/gb/london-city-of/london` it is `gb/london-city-of/london`.
3. Put it in the badge address: `https://weatheo.com/badge/gb/london-city-of/london.svg`.

You can also use the search API: `https://weatheo.com/api/v1/search?q=gien`. The `key` field of each entry in `results` is the path to use (for example `fr/centre-val-de-loire/gien`).

## Snippets

Replace the path with your own, and keep the link pointing to the city page in the same language as the badge.

### Markdown (GitHub README or profile)

```markdown
[![Weather in Paris](https://weatheo.com/badge/fr/ile-de-france/paris.svg?lang=en)](https://weatheo.com/en/fr/ile-de-france/paris)
```

### HTML

```html
<a href="https://weatheo.com/en/fr/ile-de-france/paris"><img src="https://weatheo.com/badge/fr/ile-de-france/paris.svg?lang=en" alt="Weather in Paris" height="24"></a>
```

### BBCode (forums)

```bbcode
[url=https://weatheo.com/en/fr/ile-de-france/paris][img]https://weatheo.com/badge/fr/ile-de-france/paris.svg?lang=en[/img][/url]
```

Some forums refuse SVG images in `[img]` tags. If the badge does not show, the forum administrator has to allow SVG images; there is nothing to change on the badge side. This applies to forums such as Kikourou, Camptocamp or Randonner-léger.

### reStructuredText

```rst
.. image:: https://weatheo.com/badge/fr/ile-de-france/paris.svg?lang=en
   :target: https://weatheo.com/en/fr/ile-de-france/paris
   :alt: Weather in Paris
```

## Parameters

| Parameter | Values | Default |
| --- | --- | --- |
| `style` | `line` (one line, for example `Gien (45500) \| 5°C · Ciel couvert · AQI 26`), `card` (495x120 card: icon, large temperature, city, condition, high and low) | `line` |
| `theme` | `light`, `dark` | `light` |
| `lang` | `en`, `fr`, `de`, `zh`, `zh-hant`, `es`, `it`, `pt`, `ja`, `ko`, `ru`, `ar` | `fr` for French places, `en` elsewhere |
| `units` | `metric`, `imperial` | `metric` |

Unknown values fall back to the default. The AQI is a US-EPA-style index and appears on the line badge when it is available. For French communes with a single postcode, the postcode is shown after the name.

## FAQ

**How often is the badge updated?** About every 15 minutes. GitHub's image proxy may keep an older copy a little longer.

**Why does GitHub show an old value?** GitHub serves images through its own cache (camo). It refreshes by itself; there is nothing to do except wait.

**What happens with an unknown place?** The badge shows "place not found" and the server answers with HTTP 404. Check the path with the search API.

**Which languages are available?** English, French, German, Simplified and Traditional Chinese, Spanish, Italian, Portuguese, Japanese, Korean, Russian and Arabic. Use the `lang` parameter.

**Fahrenheit?** Add `units=imperial`.

**Is it free?** Yes. There is no JavaScript, no tracking, no cookie and no API key.

**Where does the data come from?** See the [methodology](https://weatheo.com/en/blog/methodology).

**How do I report a wrong forecast or a bug?** Open an issue in this repository with the badge address and what you expected.

## Related projects

- [weatheo-ui](https://github.com/weatheo-com/weatheo-ui): React components.
- [mcp-server-weatheo](https://github.com/weatheo-com/mcp-server-weatheo): MCP server.
- [climate-data](https://github.com/weatheo-com/climate-data): open CSV files.
- JSON API: `https://weatheo.com/api/v1/weather?place=fr/centre-val-de-loire/gien`

## License

MIT, see [LICENSE](LICENSE).
