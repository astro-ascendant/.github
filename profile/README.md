<p align="center">
  <img src="https://raw.githubusercontent.com/astro-ascendant/website/main/assets/brand/wordmark.svg" alt="Ascendant" width="360" />
</p>

<h3 align="center">Modern developer ecosystem for sidereal astrology</h3>

<p align="center">
  <a href="https://www.npmjs.com/package/astro-ascendant"><img src="https://img.shields.io/npm/v/astro-ascendant" alt="npm" /></a>
  <a href="https://pypi.org/project/astro-ascendant/"><img src="https://img.shields.io/pypi/v/astro-ascendant" alt="PyPI" /></a>
  <a href="https://github.com/astro-ascendant/ascendant-ts/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-AGPL--3.0--or--later-blue" alt="License: AGPL-3.0-or-later" /></a>
</p>

Ascendant turns a birth moment into a full sidereal chart: placements, divisional
charts, dashas, Ashtakavarga, Jaimini results, and transit searches. It hands them
to you as data you can query from TypeScript, Python, or an AI coding agent.

Calculations run on the Swiss Ephemeris and always name their method: an ayanamsa,
a house system, a school. The same birth data produces the same chart, every run.
Nothing is inferred per request and nothing is invented by a language model.

## Repositories

| Repository | What's inside | Get it |
| --- | --- | --- |
| [`ascendant-ts`](https://github.com/astro-ascendant/ascendant-ts) | Effect-first TypeScript library. Calculates placements once, then derives charts, Vimshottari, Chara and Sthira dasha, Ashtakavarga, Jaimini, and transits from that shared calculation. | `bun add astro-ascendant effect` |
| [`ascendant`](https://github.com/astro-ascendant/ascendant) | Python library returning plain dictionaries and lists: charts, dashas, yogas, Ashtakavarga, and a seven-karaka Jaimini core. | `pip install astro-ascendant` |
| [`skills`](https://github.com/astro-ascendant/skills) | Agent skills and plugins that save a birth record once, then answer questions from the stored chart with citations. Works with OpenCode, Claude Code, Codex, Cursor, Copilot, and ChatGPT. | `npx ascendant-skills install` |
| [`website`](https://github.com/astro-ascendant/website) | Documentation site and the birth chart generator. | [astro-ascendant.vercel.app](https://astro-ascendant.vercel.app/docs) |

## Features
- Named methods you can repeat. TypeScript supports 39 ayanamsas and 13 house systems. Python supports 7 ayanamsas and 5 house systems. Select a method to check its results.
- Structured results. Charts, dashas, and Ashtakavarga return typed values or plain dictionaries. Your program can use these results directly.
- One calculation for many uses. Divisional charts, dashas, Jaimini, and transits use the same calculated positions. They do not calculate the sky positions again.
- Open source. The libraries use the AGPL-3.0-or-later license. The flatlib fork uses the MIT license.

## Documentation

- [Documentation and guides](https://ascendant-docs.vercel.app/docs)
- [Chart generator](https://astro-ascendant.vercel.app/chart)
- [API reference](https://astro-ascendant.vercel.app/docs)
- [Skills and plugins](https://ascendant-docs.vercel.app/docs/skills)

## Contributing

Issues and pull requests are welcome on each repository. Start with the
[contribution guide](https://github.com/astro-ascendant/ascendant-docs/blob/main/CONTRIBUTION.md)
for docs changes, or open an issue where you found the problem.
