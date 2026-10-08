# Flight fare history — what routes actually cost, measured

**1,803,177 observed fares on 71,184 city pairs, collected continuously since
2026-06-14.** Not a search engine snapshot: the same routes are observed again and again, so what
you get here is the *distribution* of a route's price, which is the thing a live search can never
tell you. Updated daily. Source: <https://piratefly.com/?src=github>

## Files

| File | One row per | Columns |
|---|---|---|
| `fares-by-month.csv` | route × departure month | observations, median, 10th percentile, minimum |
| `routes.csv` | route | observations, median, minimum, months covered, first/last observation |
| `summary.json` | today | totals, observation window, published thresholds |
| `daily/<date>.json` | each day | the immutable daily snapshot — this directory is the series |

Prices are in EUR, per one-way fare as advertised, including the price shown at collection time.

## Most-observed routes

Today's price against the history, per route, is one click away:

| Route | Observations | Median € | Lowest € |
|---|---|---|---|
| [Tokyo → Osaka](https://piratefly.com/flights/tokyo-to-osaka?src=github) | 3,714 | 50.00 | 25.00 |
| [Phuket → Bangkok](https://piratefly.com/flights/phuket-to-bangkok?src=github) | 3,586 | 35.00 | 9.00 |
| [Osaka → Tokyo](https://piratefly.com/flights/osaka-to-tokyo?src=github) | 3,569 | 42.00 | 21.00 |
| [Paris → Milan](https://piratefly.com/flights/paris-to-milan?src=github) | 3,383 | 32.00 | 13.00 |
| [London → Edinburgh](https://piratefly.com/flights/london-to-edinburgh?src=github) | 2,868 | 24.00 | 16.00 |
| [London → Milan](https://piratefly.com/flights/london-to-milan?src=github) | 2,789 | 29.00 | 17.00 |
| [Bangkok → Phuket](https://piratefly.com/flights/bangkok-to-phuket?src=github) | 2,784 | 33.00 | 11.00 |
| [Chiang Mai → Bangkok](https://piratefly.com/flights/chiang-mai-to-bangkok?src=github) | 2,738 | 39.00 | 17.00 |
| [Seoul → Jeju City](https://piratefly.com/flights/seoul-to-jeju-city?src=github) | 2,641 | 26.00 | 10.00 |
| [London → Barcelona](https://piratefly.com/flights/london-to-barcelona?src=github) | 2,489 | 32.00 | 16.00 |
| [Hanoi → Da Nang](https://piratefly.com/flights/hanoi-to-da-nang?src=github) | 2,389 | 23.00 | 20.00 |
| [Barcelona → Milan](https://piratefly.com/flights/barcelona-to-milan?src=github) | 2,236 | 17.00 | 9.00 |
| [Belfast → London](https://piratefly.com/flights/belfast-to-london?src=github) | 2,214 | 22.00 | 16.00 |
| [Malé → Colombo](https://piratefly.com/flights/male-to-colombo?src=github) | 2,177 | 158.00 | 121.00 |
| [Singapore → Kuala Lumpur](https://piratefly.com/flights/singapore-to-kuala-lumpur?src=github) | 2,165 | 65.00 | 50.00 |

## What it answers that a flight search cannot

A search engine tells you today's price. This tells you whether today's price is *good*: the median
of what the same route has actually cost, the 10th percentile (what a good deal looks like), the
lowest ever observed, and which departure months are cheap on that route. That judgement needs a
history, and a history cannot be reconstructed after the fact — which is why this file exists.

The live version of this judgement, per route and in one call, is a free public MCP server
(`flight_price_verdict`, `cheapest_months`, `when_to_book`): <https://piratefly.com/?src=github>

## Research: when to book, which weekday, the monthly fare index

The `research/` folder holds the tables behind the study *When to book flights*: the same flight
observed at different lead times (premium over its own lowest fare by booking window), departure
weekday effect, cheapest winter cities, and a chained monthly fare index (2026-08 = 100). Charts,
method and embeddable figures: <https://piratefly.com/research/when-to-book-flights?src=github>

## Live data: the API

This file is a daily aggregate. The same history, per route and current to the last observation,
is a JSON API: free without a key (100 requests/day per IP), and a **Pro plan** that removes the
cap and skips the edge cache, for apps and pipelines that need fresh prices.
Docs and Pro checkout: <https://piratefly.com/api/?src=github>

## Method, and what it does not cover

- Every row is an observed advertised fare, stored at collection time, never a modelled estimate.
- A route × month group is published only with at least 5 observations; thinner
  groups are left out entirely instead of being filled with a plausible-looking median.
- Observation window: 2026-06-14 → 2026-10-07. Anything older than that does not exist here.
- Coverage follows where fares were found, not a designed sample: city pairs are unevenly
  represented and this is not a random sample of the world's air traffic.
- One-way advertised fares only. No taxes breakdown, no seat class, no availability guarantee, and
  a fare observed is not a fare you can still buy.

## Citing

> Piratefly flight fare history, 2026-10-08. 1,803,177 observed fares, 71,184 city pairs. <https://piratefly.com/?src=github>

Licence: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — use it, say where it came from.
