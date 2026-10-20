# The As-Received Web — Edition 01

> A dated measurement of what live websites return to an HTTP agent.
> Measured 2026-10-18. 19 of 20 hosts. No scores, no rankings.

Anyone can measure today. Nobody can measure 2026-10-18 again.

## Numbers

| Signal | Result |
|---|---|
| Sites measured | 19 |
| Answered a markdown request with markdown | 6/19 |
| Returned 200 OK and HTML for a markdown request | 2/19 |
| No llms.txt | 10/19 |
| Vary disagreement (among markdown-serving sites) | 2/6 |
| robots.txt blocks at least one AI crawler | 4/19 |
| HTML with no form element | 11/19 |
| Median HTML:markdown payload ratio | 87x |
| Largest ratio | 689.8x (www.decathlon.sg, 787,093B to 1,141B) |

## Where a machine request stops

- www.lovebonito.com — 471,353 bytes of HTML returned for a markdown request
- www.allbirds.com — 718,290 bytes of HTML returned for a markdown request

## Declared policy

- www.charleskeith.com — 1 AI agents blocked in robots.txt
- www.amazon.com — 11 AI agents blocked in robots.txt
- www.wpp.com — 2 AI agents blocked in robots.txt
- www.nytimes.com — 12 AI agents blocked in robots.txt

## Table

| Site | Category | llms.txt | Markdown | .md | Vary | Ratio |
|---|---|---|---|---|---|---|
| www.lovebonito.com | commerce-sg | PASS | GAP | TRAP | N-A | — |
| www.charleskeith.com | commerce-sg | GAP | GAP | GAP | N-A | — |
| www.decathlon.sg | commerce-sg | GAP | PASS | GAP | PASS | 689.8 |
| www.allbirds.com | commerce-global | PASS | GAP | TRAP | N-A | — |
| www.gymshark.com | commerce-global | GAP | GAP | GAP | N-A | — |
| www.warbyparker.com | commerce-global | GAP | GAP | GAP | N-A | — |
| www.shopify.com | commerce-global | PASS | GAP | GAP | N-A | — |
| www.amazon.com | commerce-global | GAP | GAP | GAP | N-A | — |
| www.ogilvy.com | agency | GAP | GAP | GAP | N-A | — |
| www.wpp.com | agency | GAP | GAP | GAP | N-A | — |
| www.publicisgroupe.com | agency | GAP | GAP | GAP | N-A | — |
| docs.stripe.com | docs | PASS | PASS | PASS | PASS | 87.4 |
| vercel.com | docs | PASS | PASS | PASS | ASYM | — |
| developers.cloudflare.com | docs | PASS | PASS | GAP | PASS | 30.0 |
| docs.anthropic.com | docs | PASS | PASS | PASS | ASYM | 64.8 |
| www.cloudflare.com | saas | PASS | PASS | PASS | PASS | 447.0 |
| stripe.com | saas | PASS | GAP | GAP | N-A | — |
| www.nytimes.com | media | GAP | GAP | GAP | N-A | — |
| www.donga.com | media | GAP | GAP | GAP | N-A | — |

## What this does not claim

- Not that any agent visited, tried, or bought anything. Server logs would be required.
- No score, no ranking.
- No impersonated AI crawler user agent; robots.txt declarations only.
- Server responses only. No browser rendering.
- One run, one date.

## Data

- [receive_layer_2026-10-18.csv](data/receive_layer_2026-10-18.csv)
- [dataset_2026-10-18.json](data/dataset_2026-10-18.json)
- [MANIFEST.md](data/MANIFEST.md)
- [sha256.txt](data/sha256.txt)

## Corrections

A claim from an earlier draft — that no sampled site publishes product or price
structured data — was disproved by checking product pages and is withdrawn. It
appears here only as a withdrawal record.
