# dmit pricing: What Premium, Eyeball and Tier 1 Plans Cost in LAX, HKG and TYO, and How to Pick

DMIT's pricing page isn't really a pricing page. It's a routing diagram with dollar signs attached. Three regions, three network profiles, at least three hardware platforms, four billing cycles, and a stock system that quietly marks plans "Out of Stock" while third-party blogs still list them at prices from six months ago.

People searching for **dmit pricing** usually want one of two things. Either they want to know what a specific plan costs *right now*, or they want the thing that actually confuses everyone: why a 2GB VPS costs $6.90 a month in one line and $12.98 a month in another line that looks nearly identical on paper. Both questions have real answers, and neither is "because DMIT is expensive."

## The three things that make DMIT's price list hard to read

Start with the network profile. Every DMIT VPS belongs to one of three profiles, and the profile — not the CPU or the RAM — is what you're paying for.

- **Premium (Pro)** — China Telecom CN2 GIA (AS4809) on the return path, with Premium transit partners on top of DMIT's own backbone.
- **Eyeball (EB)** — CMIN2-oriented routing, generally the better value of the two China-optimised options, and usually the mobile-friendly one.
- **Tier 1 (T1)** — plain international routing. No mainland China optimisation at all, which is exactly why the traffic allowances are enormous and the bandwidth ports go to 10Gbps.

Second, the platform generation. DMIT's cart splits machines by CPU generation, and prices differ between them: AS3 runs AMD EPYC 7003, AN4 runs EPYC 9004, AN5 runs EPYC 9005. A "LAX.Pro.TINY" from one generation is not priced the same as the same name from another. When someone tells you DMIT raised prices, they're usually comparing an AN4 snapshot against an AN5 cart.

Third, stock. DMIT releases capacity in batches. Plans appear and disappear from the cart within hours, and the ones that go fastest are the cheap annual ones. This is why you'll find price tables on blogs that don't match what you see when you actually click through.

> The cart is the only price list that matters. Everything below is a snapshot of what the cart and reputable trackers showed when this was written — confirm the number on the order page before you pay.

That caveat out of the way, here's the structure.

## What the money actually buys: routes and overage behaviour

Two billing mechanics matter more than the sticker price.

The first is the overage model. DMIT doesn't cut you off when you burn through your monthly traffic allowance. It throttles you and lets you keep going unmetered. Premium plans typically drop to 2Mbps, 4Mbps, 8Mbps or 10Mbps depending on tier — 4Mbps on TINY and Pocket, 8Mbps on MINI and MICRO, 10Mbps on MEDIUM and above. Tier 1 plans throttle much higher, generally between 100Mbps and 500Mbps. For a low-traffic site or a proxy that spikes occasionally, the throttled-unlimited model is worth more than an extra 500GB of meter.

The second is that hardware is largely shared across profiles. The same AN5 generation, the same SSD storage, the same KVM virtualisation, the same default IPv4 plus an IPv6 /64. If a Premium plan costs 60% more than the Eyeball plan with the same RAM and disk, that difference is the route, not the machine.

So what is the route worth? Depends entirely on who your traffic is for. Premium is the pick when latency to mainland China is the product — return paths on all three carriers run CN2 GIA. Eyeball is the compromise: CMIN2 return, AS9929/AS58807 load balancing, decent numbers without the Premium surcharge. Tier 1 is for everyone else — overseas audiences, cross-border transit, downloads, backups — and it's where DMIT's prices start looking ordinary.

## Los Angeles: where most of the price ladder actually lives

LAX is DMIT's busiest region and the one with the most granular pricing. Three profiles, each with its own ladder.

### LAX.AN5.Pro — Premium, CN2 GIA

| Plan | vCPU | RAM | SSD | Traffic / Port | After overage | Price / month |
| --- | --- | --- | --- | --- | --- | --- |
| TINY | 1 | 2GB | 20GB | 1TB @ 1Gbps | 4Mbps unmetered | $12.98 |
| Pocket | 1 | 2GB | 40GB | 1.5TB @ 4Gbps | 4Mbps unmetered | $18.90 |
| STARTER | 2 | 2GB | 80GB | 3TB @ 10Gbps | 4Mbps unmetered | $38.90 |
| MINI | 2 | 4GB | 80GB | 5TB @ 10Gbps | 8Mbps unmetered | $79.90 |
| MICRO | 4 | 4GB | 160GB | 7TB @ 10Gbps | 8Mbps unmetered | $110.90 |
| MEDIUM | 6 | 8GB | 160GB | 14TB @ 10Gbps | 10Mbps unmetered | $289.90 |
| LARGE | 8 | 16GB | 320GB | 25TB @ 10Gbps | 10Mbps unmetered | $499.90 |
| GIANT | 12 | 24GB | 640GB | 50TB @ 10Gbps | 10Mbps unmetered | $1,009.90 |

👉 [Check the current LAX Premium cart prices](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=premium&aff=12046)

A word of honesty about that table: the TINY-through-STARTER figures come from trackers that agree with each other closely (the quarterly prices they list — $37.99 and $56.70 — line up with the monthly numbers). The MINI-and-up figures are what the official cart displayed, and they're noticeably higher than what several blogs still publish for the same plan names. The gap is the AN5 relaunch. Entry-level LAX Pro started at $9.99/month on AN4; the current generation starts at $12.98/month. Annual pricing on the entry tier has been reported around $119.99/year.

You can pay quarterly or annually instead of monthly, and the effective monthly rate drops. Quarterly TINY lands at $37.99, and annual billing is cheaper again.

### LAX.AN5.EB — Eyeball, CMIN2

| Plan | vCPU | RAM | SSD | Traffic / Port | After overage | Price / month |
| --- | --- | --- | --- | --- | --- | --- |
| TINY | 1 | 2GB | 20GB | 1.5TB @ 2Gbps | 4Mbps unmetered | $12.98 |
| Pocket | 2 | 2GB | 40GB | 3TB @ 4Gbps | 4Mbps unmetered | $18.90 |
| STARTER | 2 | 2GB | 80GB | 5TB @ 10Gbps | 4Mbps unmetered | $38.90 |
| MINI | 4 | 4GB | 80GB | 10TB @ 10Gbps | 8Mbps unmetered | $76.90 |
| MICRO | 4 | 4GB | 160GB | 14TB @ 10Gbps | 8Mbps unmetered | $99.90 |
| MEDIUM | 6 | 8GB | 160GB | 30TB @ 10Gbps | 10Mbps unmetered | $219.90 |
| LARGE | 8 | 16GB | 320GB | 50TB @ 10Gbps | 10Mbps unmetered | $459.90 |
| GIANT | 12 | 24GB | 640GB | 100TB @ 10Gbps | 10Mbps unmetered | $839.90 |

👉 [Compare Eyeball plans and availability](https://www.dmit.io/aff.php?aff=12046)

Look at TINY versus MINI in that table and you can see what DMIT is actually selling. Both are Eyeball, both run AN5 hardware — but the MINI hands you more than six times the traffic allowance for roughly six times the money. The RAM and CPU barely move. If your workload is bandwidth-driven rather than compute-driven, the ladder is priced almost entirely by transferred bytes.

### LAX.AN5.T1 — Tier 1, international routing

Tier 1 splits into two sub-series. VOLUME rows carry more traffic; GENERAL rows carry more CPU and memory for the same money band.

| Plan | vCPU | RAM | SSD | Traffic / Port | After overage | Price / month |
| --- | --- | --- | --- | --- | --- | --- |
| T1.V2C2G | 2 | 2GB | 40GB | 5TB @ 10Gbps | 100Mbps unmetered | $14.90 |
| T1.V2C4G | 2 | 4GB | 80GB | 10TB @ 10Gbps | 200Mbps unmetered | $23.90 |
| T1.V4C4G | 4 | 4GB | 120GB | 20TB @ 10Gbps | 200Mbps unmetered | $36.90 |
| T1.V4C8G | 4 | 8GB | 160GB | 40TB @ 10Gbps | 500Mbps unmetered | $52.90 |
| T1.V8C16G | 8 | 16GB | 240GB | 80TB @ 10Gbps | 500Mbps unmetered | $119.90 |
| T1.V12C24G | 12 | 24GB | 320GB | 160TB @ 10Gbps | 500Mbps unmetered | $199.90 |
| T1.G2C4G | 2 | 4GB | 80GB | 4TB @ 10Gbps | 100Mbps unmetered | $16.90 |
| T1.G4C8G | 4 | 8GB | 160GB | 8TB @ 10Gbps | 100Mbps unmetered | $36.90 |
| T1.G8C16G | 8 | 16GB | 320GB | 12TB @ 10Gbps | 200Mbps unmetered | $79.90 |
| T1.G12C24G | 12 | 24GB | 480GB | 24TB @ 10Gbps | 200Mbps unmetered | $119.90 |
| T1.G16C32G | 16 | 32GB | 640GB | 32TB @ 10Gbps | 200Mbps unmetered | $199.90 |

👉 [Browse the Tier 1 configurations](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=tier-1&category=general&aff=12046)

The comparison worth internalising: at $36.90 a month you can have 80GB of SSD and 3TB of CN2 GIA traffic on Pro STARTER, or 120GB of SSD and 20TB of international traffic on T1.V4C4G. Same money, completely different product. DMIT isn't hiding a better deal in the Tier 1 column — it's selling a different thing.

## Hong Kong and Tokyo: paying for proximity

Hong Kong is DMIT's shortest hop to the mainland, and the pricing reflects it. Trackers measuring the Premium series put Hong Kong to mainland China average latency around 43ms across all three carriers, with almost no packet loss — numbers nothing in North America will match.

Hong Kong pricing, by profile:

| Profile | Entry plan | Specs | Price / month |
| --- | --- | --- | --- |
| HKG.Pro (Premium, CN2 GIA) | TINY | 1 vCPU / 1GB / 20GB SSD / 500GB @ 1Gbps | $39.90 |
| HKG.Pro (Premium, CN2 GIA) | STARTER | 1 vCPU / 2GB / 40GB SSD / 1TB @ 1Gbps | $79.90 |
| HKG.Pro (Premium, CN2 GIA) | MINI | 2 vCPU / 2GB / 60GB SSD / 1.5TB @ 1Gbps | $119.90 |
| HKG.EB (CMIN2 return) | Entry | 1 vCPU / 1GB / 20GB SSD / 1TB @ 1Gbps | $29.90 |
| HKG.T1 (international) | WEE | 1 vCPU / 1GB / 20GB SSD / 1TB @ 4Gbps | $36.90 / year |
| HKG.T1 (international) | TINY | 1 vCPU / 1GB / 20GB SSD / 2TB @ 4Gbps | $6.90 |

Tokyo sits between the two. Premium entry lands around $21.90/month for 1 vCPU, 1GB and 500GB of CN2 traffic; the Eyeball equivalent starts at $25.90/month with a larger 1TB allowance on a 1Gbps port. Higher tiers in both regions run into the hundreds per month — a Hong Kong Premium GIANT with 16GB of RAM and 6TB of traffic lists around $499.90/month, and Tokyo's top configurations exceed that.

Notice the shape of it: Hong Kong Pro TINY costs about three times what LAX Pro TINY costs, for a fraction of the RAM. Nobody is buying Hong Kong Premium for the specification. They're buying a 43ms round trip and a native Hong Kong IP.

Hong Kong and Tokyo Tier 1 pricing, meanwhile, is genuinely cheap — the WEE plans are $36.90 a year — but Tier 1 Hong Kong traffic does not get mainland-optimised routing, and for a China Telecom user the latency can end up worse than a Los Angeles connection. It's a real trap for anyone who sees "Hong Kong" and assumes "fast for China."

👉 [See which Hong Kong and Tokyo plans are in stock](https://www.dmit.io/aff.php?aff=12046)

## Billing cycles, coupons and the real monthly number

DMIT prices by cycle, and the cycle changes the maths. Monthly rates are the highest. Quarterly and semi-annual orders get a smaller effective monthly rate, and annual orders get the biggest cut — entry LAX Pro annual pricing has been tracked at around $119.99/year, against roughly $156 if you paid monthly.

On top of the cycle discount, DMIT circulates coupon codes. These rotate, and the ones that circulate most widely among trackers are:

- `Lite-Annually-Recur-30OFF` — 30% off, annual billing, Standard (formerly Lite) network series
- `Lite-Semi-Annually-Recur-20OFF` — 20% off, semi-annual billing, same series
- `LAX-EB-LAUNCH-NON-MONTHLY-RECURRING-20OFF` — 20% off Eyeball plans on non-monthly cycles, recurring
- `202510_HKG_TYO_PRO_20OFF_RECURRING` — 20% off Hong Kong and Tokyo Premium on quarterly or longer cycles

The word "recurring" is the one to look for. A recurring code applies to renewals too, not just the first invoice, which changes the long-run cost considerably. DMIT also runs seasonal promotions under names like `2025-XMAS-…`, and those should be assumed dead once the season passes.

Every code gets validated at checkout — DMIT's order form has a "Validate Code" button, and an expired or inapplicable code simply won't apply. Codes are also scoped: a Tier 1 code won't work on Premium, and a monthly order won't accept a non-monthly code.

> Also worth knowing: customisations are billed separately from the headline plan price. Extra IPv4 addresses, additional RAM and SSD, and bandwidth upgrades are all add-on line items at checkout. The number in the price table is the base configuration.

## Choosing a plan without overpaying

The pricing structure answers most of the decision for you, if you're honest about two things: where your users are, and whether you're buying bandwidth or compute.

- **Cheapest way in:** Tier 1 WEE at $36.90/year. One core, 1GB, 20GB SSD, 1TB of traffic on a 4Gbps port. Fine for a small site, a monitoring node, or development. Useless if you need fast access from China.
- **China-facing on a budget:** Eyeball TINY at $12.98/month. CMIN2 return routing, 1.5TB of traffic, and the `LAX-EB-LAUNCH-…` code applies if you're not paying monthly.
- **Telecom-heavy mainland audience:** Premium, not Eyeball. Pro TINY at $12.98/month gives you 1TB on a 1Gbps port with CN2 GIA on the return path — less traffic than the Eyeball equivalent for the same money, but a better route for China Telecom specifically. That trade is the whole point of the tier.
- **High-traffic, non-China:** Tier 1 VOLUME. T1.V2C4G gives you 10TB at $23.90/month. Nothing in the Premium or Eyeball ladders comes close on cost per terabyte.
- **Compute-heavy workloads:** Tier 1 GENERAL. G4C8G is 4 cores and 8GB with 8TB of traffic at $36.90/month, the same price as a Pro STARTER with 2GB of RAM.
- **Hong Kong latency matters:** HKG.T1 if you can live with international routing, HKG.Pro if you can't.

If you only remember one rule about DMIT pricing, make it this: the price ladder is mostly a bandwidth ladder wearing a specification costume. Match the profile to your route, then buy the smallest configuration that carries your traffic.

👉 [Pull up the live cart and check today's prices and stock](https://www.dmit.io/aff.php?aff=12046)

## Common pricing questions, answered briefly

**Is there a free tier or trial?** No. DMIT doesn't publish a free plan, and the entry cost is the $36.90/year Tier 1 WEE.

**Why doesn't the price on a blog match the cart?** Because plans move between generations, get restocked in batches, and sell out. Third-party tables are snapshots, often several months old.

**What happens when I exceed my traffic?** You get throttled, not suspended. Speeds drop to somewhere between 2Mbps and 10Mbps on Premium and Eyeball, and much higher — 100Mbps to 500Mbps — on Tier 1.

**How do I pay?** PayPal, Alipay and major credit cards are all supported, which removes the foreign-card problem for most international buyers.

**Do the prices change on renewal?** With a recurring coupon, the discounted rate carries over. Without one, renewal is at list price for whatever cycle you chose.

**Can I upgrade a plan later?** DMIT supports configuration upgrades, priced as separate add-ons. Whether a specific upgrade path exists for your plan is worth confirming with support before you buy small.

The last thing worth saying is the thing that makes DMIT's pricing frustrating and trustworthy at the same time. It's expensive on the Premium side — genuinely, not marginally. But the pricing is honest about what it's selling: a route, a traffic allowance, and a generation of hardware, priced separately instead of bundled into one opaque number. Once you can read the structure, the choice gets much less complicated.
