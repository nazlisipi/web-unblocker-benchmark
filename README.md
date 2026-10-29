# Web Unblocker Benchmark

AIMultiple benchmark of Bright Data, Firecrawl, Nimble and Zyte on pages from the top 10,000 domains, measuring success rate and completion time at 5, 100, 500 and 5,000 concurrent requests.

> [Read the benchmark on AIMultiple](https://aimultiple.com/web-unblockers)

## Workload

Pages come from the top 10,000 domains in the Tranco list, minus dead, infrastructure-only, blocklisted, low-trust or keyword-flagged domains and those with fewer than 3 crawlable URLs. AIMultiple stored a CSS selector and a visible text snippet per URL. Each concurrency level used a separate URL set, and the providers received 260,000 requests in total.

- Fail: a bot-block or CAPTCHA page, or a status under 200 or 400 and above (404 excepted).
- Success: status 201-399 or 404, or a 200 response containing the stored selector or text snippet.
- Time: mean completion time of successful requests.

## Benchmark results

Success rate and mean completion time, from the article's chart:

| Provider | 5 concurrent | 100 concurrent | 500 concurrent | 5,000 concurrent |
| --- | ---: | ---: | ---: | ---: |
| Bright Data | 94% / 4 s | 94% / 4 s | 95% / 8 s | 92% / 16 s |
| Zyte | 92% / 14 s | 92% / 13 s | 93% / 12 s | n/a |
| Nimble | 90% / 10 s | 90% / 8 s | 90% / 8 s | n/a |
| Firecrawl | 88% / 4 s | 88% / 4 s | 88% / 6 s | 88% / 20 s |

Load changed completion time more than success rate: Firecrawl held 88% at every level while slowing from 4 s to 20 s. Zyte ranked second on success but had the longest times. A separate markdown test on 10,000 URLs added Exa: Bright Data 79%, Firecrawl 71%, Nimble 70%, Exa 68%.

## Scope

Results reflect the tested domains and provider settings as of August 25, 2026; live sites and anti-bot systems change. Zyte was not tested at 5,000 concurrent requests, and the chart has no 5,000 result for Nimble.

## Ownership

The benchmark implementation was developed for AIMultiple and belongs to AIMultiple. This repository contains a documentation summary. Source code and benchmark datasets are not distributed here.
