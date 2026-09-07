# cheap vps hosting 2026: how to actually find a $4/month VPS that doesn't fall apart

If you typed "cheap vps hosting 2026" into a search box, you're probably not chasing a brand name. You want a virtual private server that costs roughly the price of a coffee per month, runs your stuff without dying at 8 PM, and doesn't surprise you with a renewal hike or a bandwidth overage bill. That's a narrower ask than the marketing pages make it look.

Most "cheapest VPS" roundups in 2026 list the same handful of names — IONOS, Namecheap, Hostinger, DigitalOcean — and then quietly skip the part where the $1/month intro jumps to $9/month at renewal, or where "unlimited bandwidth" actually means "we throttle you after 2 TB." The genuinely cheap-and-stable tier lives in a less flashy corner: self-managed KVM providers that own their hardware and skip the managed-support markup. BandwagonHost (operated by IT7 Networks since 2004) sits in that corner, and it's the one this article uses as the worked example — but the buying logic applies to the whole category.

## What "cheap" actually means in 2026

A VPS is only cheap in two senses:

- **Low sticker price**: under about $5/month equivalent, ideally billed annually so you're not paying monthly-markup rates.
- **Stable renewal**: the price you pay the first year is the price you pay the third year. No "promo then double" trick.

The second point is where most cheap-looking plans fail. A $1 first-year VPS that renews at $12/month was never a $1 VPS — it was an $11 VPS with a coupon. BandwagonHost's plans are explicitly self-managed, which is how they keep the sticker low, and the recurring promo codes (more on those below) apply to renewals too, so the discount doesn't vanish after month 12.

The trade-off is honest: self-managed means there's no helpdesk installing WordPress for you. You get root, KiwiVM (their in-house panel), OS reloads, snapshots, rDNS, and free datacenter migration. You don't get someone answering "how do I configure nginx" at 3 AM. If you can follow a Linux tutorial, you're fine. If you want cPanel and hand-holding, this tier — not just BandwagonHost, the whole cheap-KVM tier — isn't for you.

## The four plan tiers, and which one maps to your actual need

BandwagonHost splits its catalog into four product lines, and the difference between them is almost entirely about **network routing**, not raw specs. A 20 GB / 1 GB RAM box costs $49.99/year on the Basic line and $169.99/year on the E-Commerce line — same storage, same RAM, same CPU cores. What you're paying for is the route to China and the uplink speed.

**Basic VPS** — commodity KVM on standard international transit. 1 Gbps uplink, 11 datacenters (US, Canada, Netherlands). This is the "I just need a Linux box somewhere" tier. Cheapest entry: $49.99/year for 20 GB SSD / 1 GB RAM / 1 TB transfer.

**E-Commerce VPS** — adds premium China routing (CN2 GIA / CTGNet, CMIN2, China Unicom Premium) and bumps the uplink to 2.5–10 Gbps. 15 datacenters including LA, Tokyo, Amsterdam, Dubai, Vancouver. The name is misleading — it's not about shopping carts, it's about "your users are in China and you don't want packet loss at peak hours." Cheapest entry: $49.99/quarter ($169.99/year) for the same 20 GB / 1 GB spec, but on a 2.5 Gbps CN2 GIA link.

**E-Commerce SLA VPS** — same network as E-Commerce, but only in Los Angeles (USCA_5), on Tier III hardware with dual power feeds, dual NICs, and a 99.99% uptime SLA with service credits. This is the "my business actually loses money when it's down" tier. Entry: $65.89/quarter for 20 GB / ~1 GB RAM.

**Ultra VPS** — Hong Kong, Tokyo, Osaka, Singapore, all on CN2 GIA peering, lowest latency to China. 1–1.5 Gbps uplinks. This is the expensive tier: $89.99/month for the smallest Hong Kong box, climbing past $1,800/month for the big ones. It exists for latency-sensitive workloads where being in Asia matters more than price.

For the "cheap vps hosting 2026" search, the relevant tiers are **Basic** and the **entry-level E-Commerce**. The SLA and Ultra lines are real products but they're not what "cheap" means.

## The full plan table (all current configs, pulled from the official order API)

Prices below are the headline billing cycle shown on the official order page for each product. Most plans also offer quarterly / semi-annual / annual options at a discount — the table lists the lowest entry price and the annual equivalent where one exists. All configs are KVM, self-managed, with 1 dedicated IPv4 and an IPv6 /64.

### Basic VPS (standard transit, 1 Gbps)

| Plan | RAM | CPU | SSD | Transfer | Uplink | Entry price | Annual equiv. | Order |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 20G KVM | 1 GB | 2× | 20 GB | 1 TB/mo | 1 Gbps | $49.99/yr | $49.99 | [Get the 20G Basic plan](https://bwh81.net/aff.php?aff=77528&pid=44) |
| 40G KVM | 2 GB | 3× | 40 GB | 2 TB/mo | 1 Gbps | $52.99/6mo | $99.99 | [Get the 40G Basic plan](https://bwh81.net/aff.php?aff=77528&pid=45) |
| 80G KVM | 4 GB | 4× | 80 GB | 3 TB/mo | 1 Gbps | $19.99/mo | $199.99 | [Get the 80G Basic plan](https://bwh81.net/aff.php?aff=77528&pid=46) |
| 160G KVM | 8 GB | 5× | 160 GB | 4 TB/mo | 1 Gbps | $39.99/mo | $399.99 | [Get the 160G Basic plan](https://bwh81.net/aff.php?aff=77528&pid=47) |
| 320G KVM | 16 GB | 6× | 320 GB | 5 TB/mo | 1 Gbps | $79.99/mo | $799.99 | [Get the 320G Basic plan](https://bwh81.net/aff.php?aff=77528&pid=48) |
| 480G KVM | 24 GB | 7× | 480 GB | 6 TB/mo | 1 Gbps | $119.99/mo | $1,199.99 | [Get the 480G Basic plan](https://bwh81.net/aff.php?aff=77528&pid=49) |

### E-Commerce VPS (CN2 GIA / CTGNet, 2.5–10 Gbps)

| Plan | RAM | CPU | SSD | Transfer | Uplink | Entry price | Annual equiv. | Order |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 20G CN2 GIA-E | 1 GB | 2× | 20 GB | 1 TB/mo | 2.5 Gbps | $49.99/3mo | $169.99 | [Get the 20G E-Commerce plan](https://bwh81.net/aff.php?aff=77528&pid=87) |
| 40G CN2 GIA-E | 2 GB | 3× | 40 GB | 2 TB/mo | 2.5 Gbps | $89.99/3mo | $299.99 | [Get the 40G E-Commerce plan](https://bwh81.net/aff.php?aff=77528&pid=88) |
| 80G CN2 GIA-E | 4 GB | 4× | 80 GB | 3 TB/mo | 2.5 Gbps | $56.99/mo | $549.99 | [Get the 80G E-Commerce plan](https://bwh81.net/aff.php?aff=77528&pid=89) |
| 160G CN2 GIA-E | 8 GB | 6× | 160 GB | 5 TB/mo | 5 Gbps | $86.99/mo | $879.99 | [Get the 160G E-Commerce plan](https://bwh81.net/aff.php?aff=77528&pid=90) |
| 320G CN2 GIA-E | 16 GB | 8× | 320 GB | 8 TB/mo | 5 Gbps | $159.99/mo | $1,599.99 | [Get the 320G E-Commerce plan](https://bwh81.net/aff.php?aff=77528&pid=91) |
| 640G CN2 GIA-E | 32 GB | 10× | 640 GB | 10 TB/mo | 10 Gbps | $289.99/mo | $2,759.99 | [Get the 640G E-Commerce plan](https://bwh81.net/aff.php?aff=77528&pid=92) |
| 1280G CN2 GIA-E | 64 GB | 12× | 1 TB | 12 TB/mo | 10 Gbps | $549.99/mo | $5,499.99 | [Get the 1280G E-Commerce plan](https://bwh81.net/aff.php?aff=77528&pid=93) |
| 1280G CN2 GIA-E 15T | 64 GB | 12× | 1 TB | 15 TB/mo | 10 Gbps | $679.00/mo | $6,790.00 | [Get the 1280G 15T plan](https://bwh81.net/aff.php?aff=77528&pid=160) |
| 1280G CN2 GIA-E 20T | 64 GB | 12× | 1 TB | 20 TB/mo | 10 Gbps | $899.00/mo | $8,990.00 | [Get the 1280G 20T plan](https://bwh81.net/aff.php?aff=77528&pid=161) |

### E-Commerce SLA VPS (Los Angeles USCA_5 only, 99.99% SLA)

| Plan | RAM | CPU | SSD | Transfer | Uplink | Entry price | Annual equiv. | Order |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 20G SLA | ~1 GB | 2× | 20 GB | 1 TB/mo | 2.5 Gbps | $65.89/3mo | $239.99 | [Get the 20G SLA plan](https://bwh81.net/aff.php?aff=77528&pid=164) |
| 40G SLA | ~2 GB | 3× | 40 GB | 2 TB/mo | 2.5 Gbps | $116.99/3mo | $399.99 | [Get the 40G SLA plan](https://bwh81.net/aff.php?aff=77528&pid=165) |
| 80G SLA | ~4 GB | 4× | 80 GB | 3 TB/mo | 2.5 Gbps | $69.99/mo | $699.99 | [Get the 80G SLA plan](https://bwh81.net/aff.php?aff=77528&pid=166) |
| 160G SLA | ~8 GB | 6× | 160 GB | 5 TB/mo | 5 Gbps | $109.99/mo | $1,099.99 | [Get the 160G SLA plan](https://bwh81.net/aff.php?aff=77528&pid=167) |
| 320G SLA | ~16 GB | 8× | 320 GB | 8 TB/mo | 5 Gbps | $199.99/mo | $1,999.99 | [Get the 320G SLA plan](https://bwh81.net/aff.php?aff=77528&pid=168) |
| 640G SLA | ~32 GB | 10× | 640 GB | 10 TB/mo | 10 Gbps | $369.99/mo | $3,699.99 | [Get the 640G SLA plan](https://bwh81.net/aff.php?aff=77528&pid=169) |

### Ultra VPS (Hong Kong / Tokyo / Osaka / Singapore, CN2 GIA peering)

| Plan | Location | RAM | CPU | SSD | Transfer | Uplink | Entry price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 40G HK CN2 GIA | Hong Kong | 2 GB | 2× | 40 GB | 500 GB/mo | 1 Gbps | $89.99/mo | [Get the HK 40G plan](https://bwh81.net/aff.php?aff=77528&pid=95) |
| 80G HK CN2 GIA | Hong Kong | 4 GB | 4× | 80 GB | 1 TB/mo | 1 Gbps | $155.99/mo | [Get the HK 80G plan](https://bwh81.net/aff.php?aff=77528&pid=96) |
| 160G HK CN2 GIA | Hong Kong | 8 GB | 6× | 160 GB | 2 TB/mo | 1 Gbps | $299.99/mo | [Get the HK 160G plan](https://bwh81.net/aff.php?aff=77528&pid=97) |
| 320G HK CN2 GIA | Hong Kong | 16 GB | 8× | 320 GB | 4 TB/mo | 1 Gbps | $589.99/mo | [Get the HK 320G plan](https://bwh81.net/aff.php?aff=77528&pid=98) |
| 640G HK CN2 GIA | Hong Kong | 32 GB | 10× | 640 GB | 6 TB/mo | 1 Gbps | $989.99/mo | [Get the HK 640G plan](https://bwh81.net/aff.php?aff=77528&pid=122) |
| 1280G HK CN2 GIA | Hong Kong | 64 GB | 12× | 1 TB | 8 TB/mo | 1 Gbps | $1,889.99/mo | [Get the HK 1280G plan](https://bwh81.net/aff.php?aff=77528&pid=124) |
| 40G Tokyo CN2 GIA | Tokyo | 2 GB | 2× | 40 GB | 500 GB/mo | 1.2 Gbps | $89.99/mo | [Get the Tokyo 40G plan](https://bwh81.net/aff.php?aff=77528&pid=108) |
| 80G Tokyo CN2 GIA | Tokyo | 4 GB | 4× | 80 GB | 1 TB/mo | 1.2 Gbps | $155.99/mo | [Get the Tokyo 80G plan](https://bwh81.net/aff.php?aff=77528&pid=109) |
| 160G Tokyo CN2 GIA | Tokyo | 8 GB | 6× | 160 GB | 2 TB/mo | 1.2 Gbps | $299.99/mo | [Get the Tokyo 160G plan](https://bwh81.net/aff.php?aff=77528&pid=110) |
| 320G Tokyo CN2 GIA | Tokyo | 16 GB | 8× | 320 GB | 4 TB/mo | 1.2 Gbps | $589.99/mo | [Get the Tokyo 320G plan](https://bwh81.net/aff.php?aff=77528&pid=111) |
| 640G Tokyo CN2 GIA | Tokyo | 32 GB | 10× | 640 GB | 6 TB/mo | 1.2 Gbps | $989.99/mo | [Get the Tokyo 640G plan](https://bwh81.net/aff.php?aff=77528&pid=123) |
| 1280G Tokyo CN2 GIA | Tokyo | 64 GB | 12× | 1 TB | 8 TB/mo | 1.2 Gbps | $1,889.99/mo | [Get the Tokyo 1280G plan](https://bwh81.net/aff.php?aff=77528&pid=125) |
| 40G Osaka CN2 GIA | Osaka | 2 GB | 2× | 40 GB | 500 GB/mo | 1.5 Gbps | $49.99/mo | [Get the Osaka 40G plan](https://bwh81.net/aff.php?aff=77528&pid=134) |
| 80G Osaka CN2 GIA | Osaka | 4 GB | 4× | 80 GB | 1 TB/mo | 1.5 Gbps | $86.99/mo | [Get the Osaka 80G plan](https://bwh81.net/aff.php?aff=77528&pid=135) |
| 160G Osaka CN2 GIA | Osaka | 8 GB | 6× | 160 GB | 2 TB/mo | 1.5 Gbps | $165.99/mo | [Get the Osaka 160G plan](https://bwh81.net/aff.php?aff=77528&pid=136) |
| 320G Osaka CN2 GIA | Osaka | 16 GB | 8× | 320 GB | 4 TB/mo | 1.5 Gbps | $329.99/mo | [Get the Osaka 320G plan](https://bwh81.net/aff.php?aff=77528&pid=137) |
| 640G Osaka CN2 GIA | Osaka | 32 GB | 10× | 640 GB | 6 TB/mo | 1.5 Gbps | $549.99/mo | [Get the Osaka 640G plan](https://bwh81.net/aff.php?aff=77528&pid=138) |
| 1280G Osaka CN2 GIA | Osaka | 64 GB | 12× | 1 TB | 8 TB/mo | 1.5 Gbps | $1,059.99/mo | [Get the Osaka 1280G plan](https://bwh81.net/aff.php?aff=77528&pid=139) |

A note on the Osaka line: it's the cheapest Ultra option by a wide margin — the 40 GB Osaka box at $49.99/month is roughly half the Hong Kong equivalent. If you specifically want low latency to Japan and don't need Hong Kong, Osaka is the value pick within the Ultra tier. Singapore Ultra plans also exist in the catalog but stock rotates; check the order page for current availability.

## Promo codes that still work (and one that doesn't)

BandwagonHost runs a recurring-discount promo code system: enter the code at checkout, and the discount applies to every renewal, not just the first payment. As of mid-2026, the codes circulating in the community and on coupon aggregators are:

- **BWHCGLUKKB** — 6.78% recurring. This is the most widely cited "standard" code and has been around for years.
- **NODESEEK2026** — 6.77% recurring. Released in early 2026, frequently listed on Chinese-language BandwagonHost community sites.
- **ireallyreadtheterms8** — 5.5% recurring. Older code, still referenced.
- **ireadtheterms8** — 4.4% recurring. Smaller discount, same family.

The codes are not stackable — pick one, the largest being BWHCGLUKKB at 6.78%. On the $49.99/year Basic plan that's about $3.40 off, bringing the effective cost to ~$46.59/year, or roughly $3.88/month. On the $169.99/year E-Commerce 20G plan it's ~$11.53 off, to ~$158.46/year.

A caveat: at least one Chinese community tracker marked all codes as expired in early March 2026, then confirmed NODESEEK2026 working again mid-February. Promo code availability fluctuates — validate the code in the cart before paying. If a code is dead, the plans are still cheap without it; the discount is a bonus, not the reason to buy.

## How the cheap plans actually compare to the "big name" cheap VPS lists

Most 2026 "cheapest VPS" roundups feature IONOS, Namecheap, Hostinger, DigitalOcean, Vultr, and AWS Lightsail. Here's the honest comparison on the dimension that matters for "cheap":

- **Sticker price**: BandwagonHost's $49.99/year Basic ($4.17/month) undercuts DigitalOcean's $4/month entry and matches AWS Lightsail's cheapest tier. IONOS's $1/month first-year deal is cheaper upfront but renews at roughly $4–10/month depending on the config.
- **Renewal stability**: BandwagonHost prices don't jump at renewal — the same plan, same price, every year, and the promo code keeps discounting. IONOS, Namecheap, and Hostinger all use intro-then-jump pricing. AWS Lightsail and DigitalOcean are stable but start higher.
- **Bandwidth overage**: BandwagonHost suspends your VPS when you hit the transfer cap, no overage bill. DigitalOcean and Vultr bill per GB over. Lightsail caps you. IONOS and Namecheap vary by plan.
- **China routing**: not a factor for most "cheap VPS" buyers, but if it is, BandwagonHost's CN2 GIA E-Commerce tier has no real competitor at this price — the big names route through commodity ChinaNet, which congests at peak hours.

The trade-off is support. BandwagonHost is self-managed with a ticket system and a knowledge base. The big names offer varying levels of managed support, and AWS/DO have enormous documentation ecosystems and community Q&A. If you're new to Linux and want someone to call, this isn't your tier. If you can read docs and run `apt install`, the price-to-stability ratio is hard to beat.

## Picking a plan for common "cheap VPS" use cases

**Personal blog / static site / portfolio.** The 20G Basic at $49.99/year is plenty. 1 GB RAM runs a LAMP or LEMP stack for a low-traffic WordPress site, or a static site generator with headroom. Pick a US datacenter (LA or NY) for general global reach, or Amsterdam if your audience is European.

**Dev / staging / throwaway box.** Same 20G Basic. If you need more RAM for Docker Compose or a small Kubernetes node, the 40G Basic at $52.99/half-year ($99.99/year) gives you 2 GB and 2 TB transfer, which is the sweet spot for "I run a few containers and don't want to worry about it."

**Small SaaS or API backend with global users.** The 80G Basic at $19.99/month ($199.99/year) gets you 4 GB RAM and 3 TB on a 1 Gbps link. That handles a real workload — a Node.js API, a Postgres instance, a small queue worker — without sweating.

**Anything serving users in China.** Skip Basic. The 20G E-Commerce at $169.99/year is the entry point, and the reason is network quality, not specs. ChinaNet (the commodity route) drops 30%+ packets at peak hours per BandwagonHost's own documentation; CN2 GIA stays stable. If you're running a site, app, or proxy that mainland users hit regularly, the $120/year premium over Basic is where it goes.

**Mission-critical, can't go down.** E-Commerce SLA in Los Angeles. The 99.99% SLA with service credits, dual power feeds, and Tier III facility is the difference between "usually up" and "contractually up." Starts at $65.89/quarter for the smallest box.

**Lowest latency to East Asia, budget allowing.** Ultra Osaka is the value play — $49.99/month for the 40 GB box on a 1.5 Gbps CN2 GIA peering link. Hong Kong and Tokyo Ultra are noticeably more expensive for the same specs.

## Buying walkthrough (what actually happens at checkout)

1. **Pick a plan from the tables above** — the links go straight to the product page with the affiliate parameter set.
2. **Choose a datacenter** — for Basic, you can migrate between datacenters later for free, so don't overthink the initial pick. For E-Commerce, USCA_9 (LA) is the default recommendation for China-facing work. For Ultra, the datacenter is tied to the plan (HK, Tokyo, Osaka, Singapore each have their own product IDs).
3. **Pick a billing cycle** — annual is cheapest per month, quarterly is the minimum for most E-Commerce plans, monthly is available on the bigger configs.
4. **Enter a promo code** — try BWHCGLUKKB first (6.78%), fall back to NODESEEK2026 (6.77%) or ireallyreadtheterms8 (5.5%) if it's been deactivated. Click "Validate Code" before continuing.
5. **Pay** — BandwagonHost supports card, PayPal, Alipay, UnionPay, and a few crypto options. They don't store card details or auto-charge; renewals are manual, which is either a feature or an annoyance depending on your workflow.
6. **Provision** — VPS is instant. You get a KiwiVM login, root credentials, and an IP. OS reload, snapshots, and datacenter migration are all in the panel.

The 30-day money-back guarantee applies if you cancel within the first month. After that, refunds are pro-rated on annual plans at BandwagonHost's discretion — don't buy a year upfront if you're not reasonably sure you want it.

## Things to know before you commit

- **Self-managed means self-managed.** No control panel like cPanel, no one-click WordPress installer, no managed backups (snapshots are manual). You get root and a panel for infrastructure-level tasks. If "managed" is what you need, look at the higher tiers of Hostinger, Namecheap, or Liquid Web instead.
- **Bandwidth is metered, not "unlimited."** Hitting your monthly transfer cap suspends the VPS until the next cycle — no overage fee, but no service either. Pick a plan with headroom. The 1 TB on the cheapest Basic plan is fine for a blog, tight for a media-heavy site.
- **CN2 GIA is not DDoS-tolerant.** BandwagonHost's own CN2 GIA documentation notes the network has limited capacity and they nullroute IPs under attack. If you're running something attack-prone, the commodity Basic line (which rides ChinaNet) actually handles DDoS better due to its bulk capacity.
- **bandwagonhost.com is blocked in mainland China.** Use the mirror domain `bwh81.net` (or `bwh88.net` / `bwh89.net`) — the affiliate links in the tables above already point to the mirror. The mirror sets the affiliate cookie correctly and shows the same catalog.
- **Some BandwagonHost IP ranges are flagged on ChatGPT and similar services.** If you're buying a VPS specifically to access AI tools via proxy, check the IP reputation before committing to a year — this isn't unique to BandwagonHost, but it's a known issue in the community.

## The short version

For "cheap vps hosting 2026," the genuinely cheap-and-stable answer is a self-managed KVM box at around $4–5/month equivalent, billed annually, with no renewal hike. BandwagonHost's **20G Basic at $49.99/year** (≈$4.17/month, less with the BWHCGLUKKB code) is the canonical example — 1 GB RAM, 20 GB SSD, 1 TB transfer, 1 Gbps, 11 datacenters, free migration. If your users are in China, the **20G E-Commerce at $169.99/year** (≈$14.17/month) is the same spec on a 2.5 Gbps CN2 GIA link and is the actual value pick for that use case. Everything above those two is for people who've outgrown the entry tier or have specific latency, SLA, or capacity needs.

If you want to compare against the big names, the test is the same: check the renewal price, not the intro price; check what happens when you hit the bandwidth cap; and check whether "managed" is worth the 3–5× markup for your actual skill level. The cheap VPS market in 2026 is more crowded than ever, but the underlying trade-off hasn't changed — you pay for support, or you pay for specs. BandwagonHost bets you'll take specs.

👉 [Browse all current BandwagonHost plans and apply the promo code at checkout](https://bit.ly/BandWaGon)
