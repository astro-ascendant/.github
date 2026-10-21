<p align="center">
  <img src="https://raw.githubusercontent.com/astro-ascendant/ascendant-ts/main/assets/wordmark.webp" alt="Ascendant" width="360" />
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
| [`ascendant-agents`](https://github.com/astro-ascendant/ascendant-agents) | Agent skills and plugins that save a birth record once, then answer questions from the stored chart with citations. Works with OpenCode, Claude Code, Codex, Cursor, Copilot, and ChatGPT. | `opencode plugin add opencode-ascendant` |
| [`ascendant-docs`](https://github.com/astro-ascendant/ascendant-docs) | Documentation site and the birth chart generator. | [ascendant-docs.vercel.app](https://ascendant-docs.vercel.app/docs) |

## Quick start

**TypeScript**

```typescript
import { AstroParams, Chart } from "astro-ascendant";
import * as Swisseph from "astro-ascendant/swisseph";
import { DateTime, Effect, Layer } from "effect";

const input = Chart.ChartParams.make({
  moment: Chart.Moment.make({ date: DateTime.makeUnsafe("2000-01-01T12:00:00.000Z") }),
  latitude: 12.9716,
  longitude: 77.5946,
});

const layers = Layer.merge(AstroParams.DefaultAstroParams, Swisseph.SwissephLayer);
const result = await Effect.runPromise(Chart.generate(input, [9]).pipe(Effect.provide(layers)));
```

**Python**

```python
from ascendant import Ascendant

astro = Ascendant(
    year=1990, month=1, day=1, hour=12, minute=0, second=0,
    utc="+5:30", latitude=28.6139, longitude=77.2090,
)

chart = astro.get_chart(division=1)
dasha = astro.get_current_dasha()
```

**Agents**

Describe the birth details and ask a question. The skill stores the record, then
answers from it. KP is the default; ask for Parashari to switch, and the two are
never mixed.

```console
npx skills add thaletto/ascendant-agents --skill ascendant
```

## What we build on

- **Named, repeatable methods.** 39 ayanamsas and 13 house systems in TypeScript;
  seven ayanamsas and five house systems in Python. You pick the method, so you
  can check the result.
- **Structured output.** Charts, dashas, and Ashtakavarga come back as typed
  values or plain dictionaries, not prose, so they compose with the rest of your
  program.
- **One calculation, many views.** Divisional charts, dashas, Jaimini, and
  transits all derive from the same placements rather than recomputing the sky
  from scratch.
- **Open source.** The libraries are AGPL-3.0-or-later. The `flatlib` fork is MIT.

## Documentation

- [Documentation and guides](https://ascendant-docs.vercel.app/docs)
- [Chart generator](https://astro-ascendant.vercel.app/chart)
- [API reference](https://astro-ascendant.vercel.app/docs)
- [Skills and plugins](https://ascendant-docs.vercel.app/docs/skills)

## Contributing

Issues and pull requests are welcome on each repository. Start with the
[contribution guide](https://github.com/astro-ascendant/ascendant-docs/blob/main/CONTRIBUTION.md)
for docs changes, or open an issue where you found the problem.
