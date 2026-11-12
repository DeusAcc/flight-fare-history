# Flight fare history — what routes actually cost, measured

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23290390.svg)](https://doi.org/10.5281/zenodo.23290390)

**6,630,937 observed fares on 101,946 city pairs, collected continuously since
2026-06-14.** Not a search engine snapshot: the same routes are observed again and again, so what
you get here is the *distribution* of a route's price, which is the thing a live search can never
tell you. Updated daily. Source: <https://piratefly.com/?src=github>

## Answers: what people ask about flight prices

Each answer is computed from this dataset's observations (2026-06-14 → 2026-11-12) and
regenerated with it; the linked page has the chart and the method.

### How far in advance should you book a flight?

Book 1.5–2 months before departure. Tracking the same flights at every lead time (113,810 flights on 22,061 routes, 2026-06-14 to 2026-11-11), that window had the smallest average premium over each flight's lowest fare: +16.2%, against +48.7% in the last 3 days. [Chart and method](https://piratefly.com/research/how-far-in-advance-to-book-flights?src=github)

### Are last-minute flights cheaper?

No. In the last 3 days before departure the same flight cost on average 48.7% more than its cheapest observed fare. Comparing 34,756 flights seen both 3–4 weeks and under a week out, the late fare was higher 66.9% of the time (median +9.6%). [Chart and method](https://piratefly.com/research/are-last-minute-flights-cheaper?src=github)

### Is it cheaper to book flights months in advance?

Not much. Booking 2–3 months ahead cost on average 20.9% more than the same flight's lowest fare, more than at 1.5–2 months (+16.2%). On 30,555 flights seen both 2–3 months and 3–4 weeks out, the early fare was higher 44.7% of the time: a coin toss. [Chart and method](https://piratefly.com/research/is-it-cheaper-to-book-flights-months-in-advance?src=github)

### What is the cheapest day of the week to fly?

Wednesday. Comparing each fare with the median of its own route, Wednesday departures were +4% and Tuesday +4.2%, while Friday was the dearest at +10.1%. Weekend departures cost more than midweek ones. [Chart and method](https://piratefly.com/research/cheapest-day-to-fly?src=github)

### What are the cheapest cities to fly to this winter?

Milan (median €29), London (median €30), Palermo (median €31). That is the median one-way fare for departures from 2026-11-01, across 349 cities ranked from fares we observed, counting only cities reachable from at least 50 airports. [Chart and method](https://piratefly.com/research/cheapest-cities-to-fly-to-in-winter?src=github)

### Are flights getting more expensive?

Not right now. The Piratefly monthly Fare Index stands at 98.7 in 2026-11 (month in progress), against 100 in 2026-08: comparable flights are 1.3% cheaper than then, measured on the same routes month to month. [Chart and method](https://piratefly.com/research/are-flights-getting-more-expensive?src=github)

### What is the cheapest month to fly?

November 2026. Comparing each route's fares month by month (booked 8–60 days ahead), November 2026 departures were -1.2% against the route's own median, while January 2027 was the dearest at +21.7%. Covers September 2026, October 2026, November 2026, December 2026, January 2027; fares observed 2026-06-14 to 2026-11-11. [Chart and method](https://piratefly.com/research/cheapest-month-to-fly?src=github)

### Are domestic flights cheaper than international flights?

Yes. The median one-way fare on a domestic route was €122, against €161 for international flights within the same continent and €270 for intercontinental ones (80,206 routes, fares observed 2026-06-14 to 2026-11-11). [Chart and method](https://piratefly.com/research/are-domestic-flights-cheaper-than-international?src=github)

### How much does a flight in Europe cost?

€115 one way at the median, across 28,860 routes within Europe (fares observed 2026-06-14 to 2026-11-11). The cheapest countries to fly to were Albania (€58), Malta (€64.5), Italy (€77); the dearest Belarus (€299) and Russia (€291). [Chart and method](https://piratefly.com/research/how-much-does-a-flight-in-europe-cost?src=github)

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
| [Osaka → Tokyo](https://piratefly.com/flights/osaka-to-tokyo?src=github) | 7,256 | 42.00 | 21.00 |
| [Tokyo → Osaka](https://piratefly.com/flights/tokyo-to-osaka?src=github) | 7,235 | 50.00 | 24.00 |
| [Phuket → Bangkok](https://piratefly.com/flights/phuket-to-bangkok?src=github) | 6,558 | 36.00 | 9.00 |
| [Paris → Milan](https://piratefly.com/flights/paris-to-milan?src=github) | 6,323 | 33.00 | 13.00 |
| [Seoul → Jeju City](https://piratefly.com/flights/seoul-to-jeju-city?src=github) | 5,633 | 25.00 | 10.00 |
| [Chiang Mai → Bangkok](https://piratefly.com/flights/chiang-mai-to-bangkok?src=github) | 5,215 | 41.00 | 17.00 |
| [London → Edinburgh](https://piratefly.com/flights/london-to-edinburgh?src=github) | 5,119 | 26.00 | 14.00 |
| [Malé → Colombo](https://piratefly.com/flights/male-to-colombo?src=github) | 4,845 | 158.00 | 121.00 |
| [Gazipaşa → Istanbul](https://piratefly.com/flights/gazipasa-to-istanbul?src=github) | 4,787 | 53.00 | 26.00 |
| [London → Milan](https://piratefly.com/flights/london-to-milan?src=github) | 4,761 | 31.00 | 16.00 |
| [Rio de Janeiro → SÃ£o Paulo](https://piratefly.com/flights/rio-de-janeiro-to-sa-o-paulo?src=github) | 4,354 | 62.50 | 25.00 |
| [IZM → Istanbul](https://piratefly.com/flights/izm-to-istanbul?src=github) | 4,348 | 27.00 | 17.00 |
| [Bangkok → Phuket](https://piratefly.com/flights/bangkok-to-phuket?src=github) | 4,331 | 34.00 | 11.00 |
| [Hanoi → Da Nang](https://piratefly.com/flights/hanoi-to-da-nang?src=github) | 4,307 | 23.00 | 19.00 |
| [London → Barcelona](https://piratefly.com/flights/london-to-barcelona?src=github) | 4,262 | 35.00 | 16.00 |

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
weekday effect (`weekday.csv`), departure-month effect (`departure-month.csv`), domestic vs
international vs intercontinental fares (`route-types.csv`), median fare by European destination
country (`europe-countries.csv`), cheapest winter cities, and a chained monthly fare index (2026-08 = 100). Charts,
method and embeddable figures: <https://piratefly.com/research/when-to-book-flights?src=github>

## Live data: the API

This file is a daily aggregate. The same history, per route and current to the last observation,
is a JSON API of booking verdicts (buy or wait, trend vs the route's history): free without a key
(30 requests/day per IP), and a **Pro plan** that removes the cap and adds watch alerts. Fares in
the API come with an affiliate booking link and the attribution "Prices by Aviasales/Travelpayouts".
Docs and Pro checkout: <https://piratefly.com/api/?src=github>

## Method, and what it does not cover

- Every value is computed from observed advertised fares stored at collection time, never a modelled estimate; no individual fare is published.
- A route × month group is published only with at least 5 observations; thinner
  groups are left out entirely instead of being filled with a plausible-looking median.
- Observation window: 2026-06-14 → 2026-11-12. Anything older than that does not exist here.
- Coverage follows where fares were found, not a designed sample: city pairs are unevenly
  represented and this is not a random sample of the world's air traffic.
- One-way advertised fares only. No taxes breakdown, no seat class, no availability guarantee, and
  a fare observed is not a fare you can still buy.

## Citing

> Piratefly flight fare history, 2026-11-12. 6,630,937 observed fares, 101,946 city pairs. DOI [10.5281/zenodo.23290390](https://doi.org/10.5281/zenodo.23290390). <https://piratefly.com/?src=github>

## Licence and source

Derived from Travelpayouts (Aviasales) affiliate data: these are Piratefly aggregates (medians, 10th percentiles, monthly minimums per route), not individual fares. Redistribution is subject to Travelpayouts' terms; this is not a CC licence and grants no sub-licence on the underlying prices. Attribution required: "Piratefly flight fare history; prices by Aviasales/Travelpayouts" with a link to https://piratefly.com.
