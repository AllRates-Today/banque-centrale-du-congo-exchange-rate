# Banque Centrale du Congo Exchange Rates API — banque-centrale-du-congo-exchange-rate

[![npm version](https://img.shields.io/npm/v/banque-centrale-du-congo-exchange-rate.svg)](https://www.npmjs.com/package/banque-centrale-du-congo-exchange-rate)
[![license](https://img.shields.io/npm/l/banque-centrale-du-congo-exchange-rate.svg)](https://github.com/AllRates-Today/banque-centrale-du-congo-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/banque-centrale-du-congo-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![USD/CDF today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbcc%3Fsource%3DUSD%26target%3DCDF&query=%24.rate&label=USD%2FCDF%20published%20by%20Banque%20Centrale%20du%20Congo&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/bcc/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbcc%3Fsource%3DUSD%26target%3DCDF&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/bcc/)

**Official Banque Centrale du Congo (DR Congo) daily exchange rates for Node.js and TypeScript. The published central bank rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers Banque Centrale du Congo itself prints, every business day.**

## 🚀 Why this client?

- 🏛️ **Official published rates** — Banque Centrale du Congo's own table, with the publisher's own `rate_date` on every response
- 📅 **History from 2026** — this source publishes only its current table, so the archive builds forward from the day we started collecting
- 🔀 **Published vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number Banque Centrale du Congo itself published, fixed once printed and carrying the central bank's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## ⚡ Try it without a key

The latest Banque Centrale du Congo table is also served keyless, CORS-open and edge-cached, for evaluation, embeds and AI agents:

```bash
curl "https://allratestoday.com/api/open/central-bank/bcc?source=USD&target=CDF"
```

```js
const r = await fetch('https://allratestoday.com/api/open/central-bank/bcc').then((x) => x.json());
console.log(r.rate_date, r.rates.length); // the central bank's latest published table, no key
```

The open endpoint serves the *latest* table only and asks for a visible attribution link. The client below uses the keyed API, which adds point-in-time tables, history, and CSV/XML/Excel output.

## 📈 Latest published table

[![Latest Banque Centrale du Congo table](https://allratestoday.com/api/open/central-bank/bcc/table.svg)](https://allratestoday.com/central-bank-rates-api/bcc/)

The image is rendered live from the keyless endpoint above, so it follows the central bank's publications on npm and on GitHub alike without a new release. The text copy below is there for search and copy-paste: on GitHub [a daily Action](.github/workflows/daily-table.yml) refreshes it whenever the central bank publishes a new table; on npm it is as of the package's publish date.

<!-- daily-table:start -->
Published **2026-10-15** by Banque Centrale du Congo — 60 rates. Updated 2026-10-15.

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| AED | CDF | buy | 603.71 |
| AED | CDF | middle | 617.64 |
| AED | CDF | sell | 631.57 |
| AOA | CDF | buy | 2.42 |
| AOA | CDF | middle | 2.475 |
| AOA | CDF | sell | 2.53 |
| AUD | CDF | buy | 1548.2 |
| AUD | CDF | middle | 1583.92 |
| AUD | CDF | sell | 1619.64 |
| BIF | CDF | buy | 0.74 |
| BIF | CDF | middle | 0.755 |
| BIF | CDF | sell | 0.77 |
| CHF | CDF | buy | 2662.56 |
| CHF | CDF | middle | 2723.99 |
| CHF | CDF | sell | 2785.42 |
| CNY | CDF | buy | 331.25 |
| CNY | CDF | middle | 338.895 |
| CNY | CDF | sell | 346.54 |
| EUR | CDF | buy | 2482.07 |
| EUR | CDF | middle | 2539.335 |
| EUR | CDF | sell | 2596.6 |
| GBP | CDF | buy | 2937.9 |
| GBP | CDF | middle | 3005.685 |
| GBP | CDF | sell | 3073.47 |
| INR | CDF | buy | 23.33 |
| INR | CDF | middle | 23.87 |
| INR | CDF | sell | 24.41 |
| JPY | CDF | buy | 14 |
| JPY | CDF | middle | 14.325 |
| JPY | CDF | sell | 14.65 |
| KWD | CDF | buy | 7112.12 |
| KWD | CDF | middle | 7276.22 |
| KWD | CDF | sell | 7440.32 |
| RWF | CDF | buy | 1.5 |
| RWF | CDF | middle | 1.535 |
| RWF | CDF | sell | 1.57 |
| SAR | CDF | buy | 591.23 |
| SAR | CDF | middle | 604.87 |
| SAR | CDF | sell | 618.51 |
| TZS | CDF | buy | 0.84 |
| TZS | CDF | middle | 0.86 |
| TZS | CDF | sell | 0.88 |
| UGX | CDF | buy | 0.54 |
| UGX | CDF | middle | 0.55 |
| UGX | CDF | sell | 0.56 |
| USD | CDF | buy | 2217.11 |
| USD | CDF | middle | 2268.27 |
| USD | CDF | sell | 2319.43 |
| XAF | CDF | buy | 3.78 |
| XAF | CDF | middle | 3.87 |
| XAF | CDF | sell | 3.96 |
| XDR | CDF | buy | 3010.85 |
| XDR | CDF | middle | 3080.315 |
| XDR | CDF | sell | 3149.78 |
| ZAR | CDF | buy | 134.55 |
| ZAR | CDF | middle | 137.655 |
| ZAR | CDF | sell | 140.76 |
| ZMW | CDF | buy | 110.87 |
| ZMW | CDF | middle | 113.43 |
| ZMW | CDF | sell | 115.99 |

Source: [Official rates published by BCC, served by AllRatesToday](https://allratestoday.com/central-bank-rates-api/bcc/). Rates are as printed by the central bank; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## 📦 Installation

```bash
npm install banque-centrale-du-congo-exchange-rate
```

```bash
yarn add banque-centrale-du-congo-exchange-rate
```

```bash
pnpm add banque-centrale-du-congo-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/banque-centrale-du-congo-exchange-rate`](https://www.npmjs.com/package/@allratestoday/banque-centrale-du-congo-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'banque-centrale-du-congo-exchange-rate';

const pair = await getRate('USD', 'CDF', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official Banque Centrale du Congo rate, on the central bank's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest published table
- [Full published table](#full-published-table) — everything the central bank printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the central bank does not print directly are resolved from its table and flagged (see *Published vs derived rates* below).

```js
const pair = await getRate('USD', 'CDF', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'bcc',
  name: 'Banque Centrale du Congo',
  rate_date: '2026-10-14',   // Banque Centrale du Congo's own publication date
  source: 'USD',
  target: 'CDF',
  rate: 2265.04,
  rate_type: 'middle',
  derived: false,
  method: 'published',
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full published table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'banque-centrale-du-congo-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'bcc',
  name: 'Banque Centrale du Congo',
  rate_date: '2026-10-14',
  rates: [
    { "base": "USD", "quote": "CDF", "type": "middle", "value": 2265.04 },
    { "base": "USD", "quote": "CDF", "type": "sell", "value": 2316.12 },
    { "base": "USD", "quote": "CDF", "type": "buy", "value": 2213.96 },
    // … the rest of the published table (21 currencies vs CDF)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2026 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'banque-centrale-du-congo-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'USD', target: 'CDF' });
```

**Response:**

```javascript
{
  bank: 'bcc',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'banque-centrale-du-congo-exchange-rate';

const series = await getHistory(
  { source: 'USD', target: 'CDF', from: '2026-01-01', to: '2026-10-14' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'bcc',
  source: 'USD',
  target: 'CDF',
  from: '2026-01-01',
  to: '2026-10-14',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-10-14', rate: 2265.04, rate_type: 'middle', derived: false, method: 'published' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'USD' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

Banque Centrale du Congo currently publishes rates covering **21 currencies** against the CDF (as of the latest table):

🇦🇪 `AED` · 🇦🇴 `AOA` · 🇦🇺 `AUD` · 🇧🇮 `BIF` · 🇨🇦 `CAD` · 🇨🇭 `CHF` · 🇨🇳 `CNY` · 🇪🇺 `EUR` · 🇬🇧 `GBP` · 🇮🇳 `INR` · 🇯🇵 `JPY` · 🇰🇼 `KWD` · 🇷🇼 `RWF` · 🇸🇦 `SAR` · 🇹🇿 `TZS` · 🇺🇬 `UGX` · 🇺🇸 `USD` · `XAF` · `XDR` · 🇿🇦 `ZAR` · 🇿🇲 `ZMW`

## 🏛️ Source

The Banque Centrale du Congo publishes the official exchange-market table for the Congolese franc every business day: mid, buying and selling rates for 21 currencies including the US dollar, euro, SDR and the regional CFA and East African units. It is the reference for customs valuation, tax and public accounting in DR Congo.

- Publisher's own page: [Marché officiel des changes](https://www.bcc.cd/marche-des-changes/cours-de-change) · [www.bcc.cd](https://www.bcc.cd)
- Publication: every business day; the exact schedule, freshness status and any current delay are on the [Banque Centrale du Congo rates page](https://allratestoday.com/central-bank-rates-api/bcc/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- Banque Centrale du Congo quotes **CDF per 1 unit of foreign currency** (e.g. `base: "USD", quote: "CDF"` means CDF per one US dollar).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- `rate_type` tells you which of the central bank's series a row belongs to (`middle` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official Banque Centrale du Congo rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/bcc/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('bcc')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate bcc ...` command
- Need dated tables or history for an evaluation? Agents can self-issue a trial key with no signup: `POST https://allratestoday.com/api/agent/keys` (send `Content-Type: application/json`) returns a 100-call key valid 7 days; the MCP servers expose it as `request_trial_key`
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Published vs derived rates

If Banque Centrale du Congo does not print a pair directly, the API resolves it from the central bank's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The central bank printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via CDF from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('USD', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by Banque Centrale du Congo |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'banque-centrale-du-congo-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('banque-centrale-du-congo-exchange-rate');

getRate('USD', 'CDF', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once per business day — cache the published table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the published table |
| `getLatestRates({ apiKey })` | Free | The central bank's full latest published table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2026 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same published tables are mirrored daily as open data:

- Hugging Face: [AllRatesToday/central-bank-exchange-rates](https://huggingface.co/datasets/AllRatesToday/central-bank-exchange-rates) — one CSV per institution (`rates/bcc.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- Raw JSON on GitHub: `https://raw.githubusercontent.com/AllRates-Today/central-bank-exchange-rates/main/data/bcc/latest.json`

## 🔗 Links

- [Banque Centrale du Congo rates page](https://allratestoday.com/central-bank-rates-api/bcc/) — live table, publication cadence, FAQ
- [All central bank sources](https://allratestoday.com/central-bank-rates-api/)
- [Package docs on the site](https://allratestoday.com/docs/sdk/banque-centrale-du-congo-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (free)](https://allratestoday.com/register) · [Pricing](https://allratestoday.com/pricing/)
- [GitHub](https://github.com/AllRates-Today/banque-centrale-du-congo-exchange-rate)

## 📜 License

MIT
