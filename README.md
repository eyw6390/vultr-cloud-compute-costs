# Cloud Server Providers: What a $5 Cloud Server Really Costs Per Month, Which Plan Fits, and How to Claim the $300 Credit (Plan Table + Billing Checklist)

Vultr's entry point for a usable cloud server is **$5/month**: 1 vCPU, 1 GB RAM, 25 GB SSD, 1 TB of bandwidth included, billable by the hour at $0.007. That's the plan most people comparing cloud server providers should start on, and it's the number to hold every other quote against.

What moves the bill after month one is everything outside the headline price: block storage, backup retention, the region you deploy in, and whether the promotional credit you signed up for covers the products you actually run. Vultr currently offers $300 in credit to new accounts, and it's one of four offers that cannot be combined.

Below is the full Cloud Compute price ladder, followed by the parts of a cloud bill that decide whether you're paying $5 or $50 a month.

> **Quick pick.** Start with the $5 Regular Performance plan (1 vCPU, 1 GB, 25 GB SSD, 1 TB bandwidth). Running a database or anything with steady CPU load? The $6 High Performance plan doubles included bandwidth to 2 TB and moves you to NVMe on current-generation EPYC for one dollar more. New accounts can put $300 of credit against the first weeks.
> 👉 [See Vultr's current plans and start with the $300 credit](https://bit.ly/VuLtr)

## The Vultr Cloud Compute lineup, all of it

Two families, both hourly and monthly billable, both with bandwidth bundled into the plan.

**Regular Performance** runs on shared vCPUs, previous-generation Intel CPUs and regular SSD. Vultr positions it for low-traffic websites, blogs, CMS installs, dev and test environments and small databases. Prices in USD, as listed on the pricing page.

| Plan | Storage | Bandwidth | Price | Deploy |
| --- | --- | --- | --- | --- |
| 1 vCPU / 512 MB (IPv6 only) | 10 GB SSD | 0.5 TB | $2.50/mo ($0.004/hr) | [Deploy](https://bit.ly/VuLtr) |
| 1 vCPU / 512 MB | 10 GB SSD | 0.5 TB | $3.50/mo ($0.005/hr) | [Deploy](https://bit.ly/VuLtr) |
| 1 vCPU / 1 GB | 25 GB SSD | 1 TB | $5/mo ($0.007/hr) | [Deploy](https://bit.ly/VuLtr) |
| 1 vCPU / 2 GB | 55 GB SSD | 2 TB | $10/mo ($0.015/hr) | [Deploy](https://bit.ly/VuLtr) |
| 2 vCPU / 2 GB | 65 GB SSD | 3 TB | $15/mo ($0.022/hr) | [Deploy](https://bit.ly/VuLtr) |
| 2 vCPU / 4 GB | 80 GB SSD | 3 TB | $20/mo ($0.030/hr) | [Deploy](https://bit.ly/VuLtr) |
| 4 vCPU / 8 GB | 160 GB SSD | 4 TB | $40/mo ($0.060/hr) | [Deploy](https://bit.ly/VuLtr) |
| 6 vCPU / 16 GB | 320 GB SSD | 5 TB | $80/mo ($0.119/hr) | [Deploy](https://bit.ly/VuLtr) |
| 8 vCPU / 32 GB | 640 GB SSD | 6 TB | $160/mo ($0.238/hr) | [Deploy](https://bit.ly/VuLtr) |
| 16 vCPU / 64 GB | 1280 GB SSD | 10 TB | $320/mo ($0.476/hr) | [Deploy](https://bit.ly/VuLtr) |
| 24 vCPU / 96 GB | 1600 GB SSD | 15 TB | $640/mo ($0.952/hr) | [Deploy](https://bit.ly/VuLtr) |

Two details in that table matter more than the rest. The $2.50 plan is IPv6-only, so a normal web app on a domain with an A record can't use it. And the two sub-$5 tiers are offered in a handful of US locations only, while the $5 plan runs in more than 30. If you're deploying a standard site for real users, $5 is the floor, not $2.50.

**High Performance** uses current-generation AMD EPYC or Intel Xeon with NVMe SSD; the Intel configurations listed on the pricing page carry the same prices for the specs shown.

| Plan | Storage | Bandwidth | Price | Deploy |
| --- | --- | --- | --- | --- |
| 1 vCPU / 1 GB | 25 GB NVMe | 2 TB | $6/mo ($0.009/hr) | [Deploy](https://bit.ly/VuLtr) |
| 1 vCPU / 2 GB | 50 GB NVMe | 3 TB | $12/mo ($0.018/hr) | [Deploy](https://bit.ly/VuLtr) |
| 2 vCPU / 2 GB | 60 GB NVMe | 4 TB | $18/mo ($0.027/hr) | [Deploy](https://bit.ly/VuLtr) |
| 2 vCPU / 4 GB | 100 GB NVMe | 5 TB | $24/mo ($0.036/hr) | [Deploy](https://bit.ly/VuLtr) |
| 4 vCPU / 8 GB | 180 GB NVMe | 6 TB | $48/mo ($0.071/hr) | [Deploy](https://bit.ly/VuLtr) |
| 4 vCPU / 12 GB | 260 GB NVMe | 7 TB | $72/mo ($0.107/hr) | [Deploy](https://bit.ly/VuLtr) |
| 8 vCPU / 16 GB | 350 GB NVMe | 8 TB | $96/mo ($0.143/hr) | [Deploy](https://bit.ly/VuLtr) |
| 12 vCPU / 24 GB | 500 GB NVMe | 12 TB | $144/mo ($0.214/hr) | [Deploy](https://bit.ly/VuLtr) |

## What cloud server providers don't put in the headline price

Three lines do most of the damage: outbound bandwidth, block storage, and backups.

Vultr bundles bandwidth into the plan, from 1 TB on the $5 server up to 15 TB on the $640 one. For a site serving images or an API answering mobile clients, that inclusion is worth more than a small gap in the hourly rate. Where egress is metered separately, the same traffic turns into its own invoice line: 5 TB of outbound at an illustrative $0.01/GB is $50 a month, ten times the cost of a $5 instance. UpCloud takes the other route and lists public outbound, inbound and private transfer at $0.00/GiB, so its pricing page never grows a traffic line at all.

Storage is where cheap plans stop being cheap. Plan storage is 25 GB on the $5 tier and 55 GB on the $10 tier; go beyond it and you're attaching block storage. UpCloud's published rates show how wide the tiers spread: **Standard $0.097/GB/month, MaxIOPS $0.250/GB/month, Archive $0.065/GB/month**. Half a terabyte of Standard comes to $48.50 a month, more than the $32 server it hangs off, and the same capacity on MaxIOPS is $125. A database whose working set fits in RAM should be on Standard or local NVMe; MaxIOPS earns its price only when you're genuinely pushing high random-read IOPS.

Backups are quoted as a percentage of the server plan on UpCloud: +10% for daily backups held 24 hours, +20% for a week, +40% for a month with weekly plus daily, +60% for a year. On a $32 plan the year option adds $19.20 monthly, a 60% raise on the compute line for something most buyers assume is included.

Region is the last multiplier. Vultr's plan API lists the $5 configuration at $5/month in most of its locations and **$7.50/month in São Paulo**. Identical specs, half again the price, because the infrastructure costs more to run there. Worth it if your users are in Brazil, an avoidable surcharge if they aren't.

## Shared vCPU or dedicated: where the cheap plans break

Hetzner separates the two tiers more clearly than most. Shared plans suit development and test environments, personal sites and blogs, small databases and web servers with low to moderate traffic, and its own copy says they're designed for variable usage rather than sustained high workloads. Dedicated vCPU plans are aimed at production applications with constantly high CPU, high-traffic sites, large databases, game servers, machine learning and bulk data processing.

Apply that rule to any provider's table. Read the CPU graph, not the spec sheet. If it spikes and idles, shared cores are fine and you should keep the money. If it sits flat at a high level all day, neighbours on the same hardware will affect your response times exactly when your users notice, and the two-dollar gap to a dedicated plan is the cheapest upgrade on the list.

On Vultr, that gap is measurable. Moving from the shared 1 vCPU / 2 GB plan at $10 to the High Performance equivalent at $12 buys 3 TB of bandwidth instead of 2 TB, NVMe instead of regular SSD, current-generation EPYC instead of previous-generation Intel, and 50 GB of included storage instead of 55 GB. For a production web app that's an easy trade. For a staging box it's $24 a year you don't need to spend.

## GPU and AI workloads: four things to verify before you commit

Almost every provider now advertises GPU instances. Four questions decide whether the GPU is actually usable for your project:

1. **Availability by model and region.** A GPU on the pricing page that is permanently out of stock where you need it is a marketing asset, not capacity.
2. **Provisioning time.** Ask what the queue is on the specific model. Three weeks of waiting damages a launch as much as a missing GPU does.
3. **Regional capacity at the size you need.** Multi-GPU nodes and the interconnects between them sell out before single cards do.
4. **Storage throughput and network latency around the GPU.** Training and inference both shuttle large datasets between compute and storage, and a fast GPU starved by slow storage finishes later than a slower one that isn't.

Vultr runs GPU instances for AI training and inference next to its general-purpose compute, which is the shape startups and digital-native teams tend to want: GPU capacity without an enterprise contract and a solutions architect attached to it. Confirm the region and the provisioning time before you build a training budget on top of it.

👉 [Check Vultr's GPU and high-performance plans](https://bit.ly/VuLtr)

## Compliance and data residency, in plain terms

SOC 2 and ISO 27001 are process audits. They say a provider has documented controls and that someone outside checked the documentation. BSI C5 is the German standard, with heavier emphasis on cloud-specific transparency. GDPR compliance is a legal obligation rather than a badge, and on its own it tells you nothing about where your data physically sits unless the provider commits to a region.

Hetzner operates its own data centre parks in Falkenstein, Nuremberg and Helsinki, plus locations in Hillsboro, Ashburn and, since 2024, Singapore. Its German and Finnish sites hold ISO/IEC 27001 certification and BSI C5, and the SLA promises 99.9% uptime with defined credits when something breaks. plusserver, also German, is a Gaia-X founding member with a BSI C5 audit and four data centres across the DACH region.

The check that matters is scope. Ask which legal entity holds the data, which certificates cover the specific data centre you'll be deployed in, and what your options are if access gets restricted. A certificate covering a headquarters building is not the same document as one covering the rack your database sits in.

## The $300 credit: what the terms actually say

Vultr's coupon page lists four offers. All four are for new customers only, all apply to select products only, and none can be combined with another.

| Code | Offer |
| --- | --- |
| FLY300VULTR | $300 free credit |
| 250VULTRFLY | $250 free credit |
| FLYTWOHUNDRED | $200 free credit |
| VULTRMATCH | Vultr matches your first deposit dollar for dollar, up to $100 |

The first three are promotional credit: it covers eligible products and starts running down as soon as it lands. The deposit match doubles your own money, up to $100, which fits an account you intend to keep funding. Burning through a few weeks of GPU or high-tier testing? Take the $300. Opening an account you'll run for a year and putting your own money in regardless? The match is the better-shaped offer.

The coupon page doesn't state the expiry window, so read the terms shown when you apply the code. Because the offers don't stack, entering the wrong one at signup costs you the difference in credit.

👉 [Read the terms on all four Vultr promo codes](https://www.vultr.com/coupons/?ref=9738262-9J)

## How the main cloud server providers compare

| Provider | What you should know |
| --- | --- |
| UpCloud | Starter plans from $3.50/mo (1 vCPU, 1 GB, 10 GB) to $32/mo, 99.99% SLA, zero-cost transfer in and out, MaxIOPS storage up to 100k IOPS. The pricing page flags changes to previous Cloud Server plans, Standard and Archive block storage, and Windows Server licences taking effect on November 16, so the figures shown today may not be what you pay next week. |
| Hetzner | Shared versus dedicated vCPU tiers, own data centre parks in Germany and Finland plus the US and Singapore, GDPR, ISO/IEC 27001 and BSI C5, 99.9% SLA with credits, 24/7 email support. |
| plusserver | German sovereign cloud, Gaia-X founding member, BSI C5 audited, four DACH data centres. The public page carrying its entry prices dates from 2023, so treat any figure from it as indicative rather than current. |

## FAQ

**Is bandwidth really included, or is there an overage charge?**
Vultr includes a monthly allowance per plan, 1 TB on the $5 server rising to 15 TB on the $640 one. Overage handling differs by region, so check the rate for your deployment location before you move a large dataset in.

**Can a shared vCPU plan run production?**
Yes when traffic is spiky or light. No when CPU sits high around the clock, which is where shared hardware starts showing up in your response times.

**What if the GPU I need isn't available in my region?**
Ask for the provisioning time on that specific model, and check that storage and network around it can keep pace. Capacity arriving in three weeks doesn't rescue a launch next week.

**What does an SLA credit actually pay?**
A percentage of the monthly fee, not the revenue you lost. Hetzner's 99.9% SLA defines credits for outages; read the schedule before treating an SLA as insurance.

**Can I pay monthly and cancel?**
Vultr lists hourly and monthly rates for every plan. At $0.007/hr, 720 hours comes to $5.04, so an instance that runs continuously is cheaper at the monthly price and one that lives for three days is cheaper by the hour.

## Which one to pick

- **A VM, bundled bandwidth and a forecastable bill:** Vultr Regular Performance at $5, or $2.50 if IPv6-only works and you're in a supported location.
- **A production app or database with steady CPU:** Vultr High Performance from $6, which is $2 above the equivalent shared plan at 1 vCPU / 2 GB.
- **GPU training or inference:** confirm the model, region and provisioning time first, then size your credit against the number you get.
- **EU data residency with audit paperwork:** a German or Finnish provider whose ISO 27001 and BSI C5 certificates cover the site you'll actually deploy in.

Two things to settle before you enter a card number. Which promo code covers the products you'll run, since the $300 credit and the deposit match are mutually exclusive. And what the second invoice looks like once block storage, snapshots and any region surcharge land on it.

👉 [Open a Vultr account and apply the $300 credit](https://www.vultr.com/coupons/?ref=9738262-9J)
