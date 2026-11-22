# iGaming hosting: bare metal with audit certificates, or a €2 VPS? Latency, DDoS scrubbing and licensing evidence compared (full AVA Hosting plan table)

Most iGaming hosting decisions reduce to one question: does your licence require you to hand a regulator evidence about the machine your platform runs on? If it does, you need a provider that publishes ISO 27001, SOC and PCI DSS documentation, and AVA Hosting is not that provider. If you are running affiliate pages, an odds feed, a bonus engine, a payment callback service or a small casino front end, AVA Hosting sells that capacity for **€2 to €40 a month**, and one of the middle plans is probably enough.

AVA Hosting runs a dedicated online-casino VPS page, so the company is actively selling into this market. What it does not publish is the paperwork a licensed operator needs, or any bare metal, private rack or hardware RNG option. That single fact decides whether you read the rest of this as a buying guide or as a reason to look elsewhere. Both outcomes are useful.

> **Quick pick:** for a casino or sportsbook front end, an affiliate/SEO network or a staging environment, the **€20 Pro plan (4 vCPU, 8 GB RAM, 100 GB NVMe)** covers a database plus application stack on one box, and **€10 Basic** covers a single site with room to spare. Both are billed monthly, both list unlimited transfer.
> 👉 [Check the current AVA Hosting VPS lineup and prices](https://my.ava.hosting/aff.php?aff=15562)

## Every AVA Hosting self-hosted plan, side by side

These six plans are the current self-hosted VPS lineup on AVA Hosting's cart. All prices are monthly, quoted "starting from", and all six list unlimited transfer and NVMe storage. The cart also flags a free trial on the entry plan; confirm its length at checkout, because it is not spelled out on the product page.

| Plan | vCPU · RAM · NVMe | Price (monthly) | What it realistically carries | Order |
| --- | --- | --- | --- | --- |
| Self-hosted Start | 1 vCPU · 1 GB · 15 GB | **€2.00** | One landing page, an affiliate tracker, a status monitor, a redirect service | [Order Start](https://my.ava.hosting/aff.php?aff=15562) |
| Mini | 1 vCPU · 2 GB · 25 GB | **€5.00** | A WordPress or static casino review site with traffic, a small bonus engine | [Order Mini](https://my.ava.hosting/aff.php?aff=15562) |
| Basic | 2 vCPU · 4 GB · 50 GB | **€10.00** | A single casino front end plus MySQL, or a game-aggregator demo environment | [Order Basic](https://my.ava.hosting/aff.php?aff=15562) |
| Pro | 4 vCPU · 8 GB · 100 GB | **€20.00** | App server, database and Redis on one machine; a mid-size sportsbook front end | [Order Pro](https://my.ava.hosting/aff.php?aff=15562) |
| Business | 6 vCPU · 12 GB · 150 GB | **€30.00** | Higher concurrency, heavier MySQL working set, in-memory caching for odds | [Order Business](https://my.ava.hosting/aff.php?aff=15562) |
| Power | 8 vCPU · 16 GB · 200 GB | **€40.00** | The top of the VPS range before you should be looking at bare metal elsewhere | [Order Power](https://my.ava.hosting/aff.php?aff=15562) |

A second table is more honest about what those prices do and do not include, because the gaps matter more here than the specs.

| Item | What AVA Hosting's pages say | What to confirm before you pay |
| --- | --- | --- |
| DDoS protection | The casino VPS page advertises DDoS protection as part of the package | Capacity, and whether scrubbing is always-on or triggered on attack |
| IPv4 | Dedicated IPv4 listed | How many, and whether extra IPs are available for affiliate/SEO fleets |
| Location | The cart page states no data centre location; two independent third-party write-ups place the company and its facility in Moldova (Chisinau) | Which country your data physically sits in, in writing |
| Certifications | None named. The casino page says the hosting "strictly complies with international security standards" without naming a standard | Whether any ISO 27001, SOC or PCI DSS report exists at all |
| Hardware | NVMe storage, virtualised | No hardware RNG, no IPMI/iLO out-of-band console, no private VLAN between instances |
| Uptime commitment | A 99.9% SLA figure appears in a third-party price tracker that read the site in September 2026 | The SLA document itself, and whether it carries service credits |
| Refunds | A 30-day money-back window is listed by the same third-party tracker | The actual terms page, and whether it applies to VPS or only shared hosting |

## What an iGaming platform is actually hosting

There are two ways to build a casino or sportsbook, and both end up needing servers.

The first is direct integration: you contract each game studio, each wallet provider and each registration portal yourself, and you carry the integration and relationship management for every one of them. The second is a game aggregator: one API integration gives you access to dozens of studios plus registration, user management and payments. The aggregator is software too, and it has to run somewhere.

Whichever route you take, three requirements push general-purpose cloud hosting out of the picture, and they are worth stating plainly because they define what you are shopping for. Live betting latency, regulatory data residency, and traffic overflow during major sporting events. A cloud VM with noisy neighbours and a shared network path handles none of these gracefully.

The commercial weight behind them is easy to understate. Leaseweb puts it as every second of downtime meaning thousands in lost revenue; NovoServe frames a single second of latency as abandoned bets, not just annoyed players. Bet365 went down twice in 2022, once just after the Aintree Grand National with punters unable to withdraw winnings, once during the Manchester City–Real Madrid Champions League match. No revenue impact was published for either, but the pattern is the part worth remembering: the withdrawal path fails alongside the betting path, and it fails at the exact moment traffic peaks.

## Four things that actually decide the purchase

### 1. Latency and peak load, measured against what you promised players

Latency budgets differ by product. A slot spin tolerates more than an in-play bet on a corner kick. What does not differ is that peak traffic arrives on a schedule you do not control: a Grand National, a Champions League knockout, a major final.

This is where the uptime numbers in vendor marketing stop being comparable. A 99.9% SLA allows roughly 43 minutes of downtime a month, or about 8.8 hours a year. 99.99% allows about 4.3 minutes a month. 99.999% allows about 26 seconds. Leaseweb's figure is explicitly "core uptime", meaning the network core, not your individual server. Gambitec quotes 99.99% for its platform. AVA's 99.9% is the lowest of the three, and it is the number that applies to the box your database sits on. Ranking these against each other is meaningless until you know what is being measured.

For a small front end, 43 minutes a month of allowance is survivable. For a sportsbook taking in-play bets, it is not, and no VPS on this list changes that.

### 2. Compliance evidence, in the specific vocabulary auditors use

The acronyms get used interchangeably in marketing copy, and they are not interchangeable.

ISO 27001 certifies a management system for information security at a facility or company. SOC reports come in types: SOC 1 covers controls relevant to financial reporting, and a Type 1 report describes control design at a single point in time, while a Type 2 report tests whether those controls actually operated over a period. SOC 2 addresses security, availability and confidentiality rather than financial reporting, and it also splits into Type 1 and Type 2. PCI DSS covers the cardholder data environment specifically.

For a licence application this matters because regulators ask for reports, not adjectives. NovoServe states that its ISO 27001 and SOC 2 facilities are usually a precondition for KSA and MGA audits. Leaseweb holds ISO 27001, SOC Type 1 and PCI DSS; Gambitec holds ISO 27001 and PCI DSS; Internet Vikings lists ISO 27001. AVA Hosting's casino page names none of them.

Two more licensing details are worth checking early, because they eliminate options rather than rank them. Some jurisdictions require the platform to sit in a private rack rather than shared infrastructure, which a VPS cannot satisfy. And if your licence requires certified random number generation, hardware RNG matters: Gambitec sells servers with hardware random number generators specifically so operators can pass GLI and iTechLabs certification. A virtualised VPS gives you no path to that.

### 3. DDoS protection that does not tax your real players

Every provider in this market advertises DDoS protection. The variable is what happens to legitimate traffic during an attack.

NovoServe describes its mitigation as "game-aware": filtering at the edge without dropping legitimate player packets or adding jitter. That is the right specification to ask about, because an aggressive filter that resets sessions during a peak betting window causes the same damage as the attack. Ask three questions: is scrubbing inline and always-on, does mitigation change your IP, and what is the capacity in Gbit/s. AVA Hosting advertises DDoS protection without publishing a capacity figure; an independent review reports "hundreds of Gbit/s" of mitigation capacity at the facility, which is a third-party claim, not a contractual one.

### 4. Isolation model: VPS, bare metal, or a rack

VPS isolation protects you from other tenants' software, not from their resource consumption on the same physical host, and it gives you root but not an out-of-band console. NovoServe's argument for bare metal is exactly this: dedicated isolation, no noisy neighbours, and IPMI 2.0 or iLO on every HPE and Supermicro server so your team can do BIOS-level configuration and remote reboots without opening a ticket. Gambitec splits the market the same way, bare metal for enterprise operators and isolated VPS for startups. Internet Vikings goes further with colocation from 1U, for operators who own hardware or whose licence demands it.

AVA Hosting sells only the VPS end of that spectrum. That is not a flaw in the product; it is a boundary, and it is the boundary that decides most of the readers of this page.

## Where AVA Hosting fits, and where it stops

The case for AVA Hosting is price against capacity, in a jurisdiction that is not the EU or the US. €20 buys 4 vCPU, 8 GB and 100 GB of NVMe billed monthly, which is a fifth of what a comparable bare metal box costs anywhere in this market. If you are building an affiliate network across many domains, running SEO properties with distributed IPs, hosting a bonus comparison site, or standing up a staging environment for a platform that lives elsewhere in production, that arithmetic is the whole argument.

The case against is short. No named certifications, so no audit evidence. No bare metal, no private rack, no IPMI. No hardware RNG, so no GLI or iTechLabs route. No published DDoS capacity in writing. A single region. If any of those five is a hard requirement in your licence, AVA Hosting cannot be your production host, and no amount of price advantage fixes it.

There is a middle path worth naming: because a Pro plan is €20, running three of them for web front end, application logic and database costs €60 a month. That buys you the tier separation NovoServe describes with private VLAN tagging (internal traffic off the public internet, lower latency between the database and the game engine). What it does not buy is private VLAN itself; AVA's pages do not mention private networking between instances, so you would build the overlay yourself with WireGuard or similar, and you would still be running on one provider in one country.

👉 [Compare the AVA Hosting plans against your own load estimate](https://my.ava.hosting/aff.php?aff=15562)

## How the established iGaming hosts line up

Pure information, for calibration. None of these four publish a price on their iGaming pages, which is itself part of the comparison.

| Provider | Footprint | Published certifications | Entry product |
| --- | --- | --- | --- |
| Leaseweb | Data centres on four continents; claims 99.999% core uptime | ISO 27001, SOC Type 1, PCI DSS | Dedicated servers, cloud, CDN, DDoS and backup services |
| NovoServe | Netherlands (Amsterdam, Rotterdam), Denmark (Copenhagen, large deployments only), US (New York); AMS-IX peering | ISO 27001, SOC 2 | Bare metal with IPMI 2.0/iLO standard, private VLAN tagging, accepts BTC, ETH and USDT |
| Internet Vikings | Per its page dated November 2023: 24 US states, Canada, Europe including Malta for MGA work — the list may have changed since | ISO 27001 | VMware cloud, bare metal, GPU servers, colocation from 1U, DR and Malta replication |
| Gambitec | US, Europe, Canada, Latin America, Arab countries; claims 99.99% uptime | ISO 27001, PCI DSS | Isolated VPS for startups through bare metal, plus jackpot, database and affiliate-specific builds, hardware RNG available |

Two patterns are consistent across all four. They name their certificates. And they compete on compliance and location rather than on the price of a VM. That is the market AVA Hosting sits outside of.

## Who should skip AVA Hosting

Skip it if you hold or are applying for an MGA or KSA licence and the auditor will ask for a SOC report. Skip it if your jurisdiction mandates a private rack. Skip it if your RNG has to be certified. Skip it if your live betting product needs a written latency SLA with credits attached, or if your DDoS exposure is measured in hundreds of Gbit/s and you need that number in a contract.

Also skip the €2 Start plan if you are running anything with a database. 1 GB of RAM is enough for Nginx and a static page; MySQL plus PHP will spend its life swapping. The honest threshold is Basic at €10 for a single site, Pro at €20 the moment you have an application server and a database on the same box.

## Questions that come up before ordering

**Do licensed operators have hard requirements on the host?**
Yes, and they are specific: ISO 27001 or SOC evidence for the facility, data residency in an approved jurisdiction, sometimes a private rack, and certified RNG where the licence demands it. NovoServe treats ISO 27001 and SOC 2 as preconditions for KSA and MGA audits; Gambitec sells hardware RNG for GLI and iTechLabs certification. A host that names none of these cannot support that application.

**Can a VPS run a live dealer product?**
The video does not run on your VPS. What runs there is the API, wallet, bonus engine and session logic, plus whatever relays the stream metadata. That layer fits comfortably on a Pro plan. Transcoding multiple video streams does not, and no VPS at this price point is the right tool for it.

**Will DDoS protection hurt real players?**
Only if it is configured badly. The failure modes are on-demand scrubbing that reroutes traffic and resets sessions, filters tuned for generic web traffic that flag high-frequency betting calls, and added jitter on a path where milliseconds cost money. NovoServe's "game-aware" description is the specification to hold vendors to; AVA Hosting advertises protection without publishing capacity, so ask before you commit.

**Monthly or annual?**
AVA Hosting's cart quotes monthly, from €2 to €40. Whether annual billing is discounted, and whether renewal stays at the same price, is not stated on the cart page. Get it in writing before you prepay a year.

## The decision, by scenario

Affiliate or SEO network, multiple domains, no player data: Start at €2 or Mini at €5, one per property, and keep them separated.

A single casino or sportsbook front end with a database, pre-launch or small player base: Basic at €10, moving to Pro at €20 once the database working set outgrows 4 GB.

A multi-service architecture where you want the front end, application logic and SQL on separate machines: three Pro instances, €60 a month, with your own private overlay network.

A licensed operation that will face an MGA, KSA or GLI audit: none of the above. Go to a provider that publishes ISO 27001 and SOC reports, offers bare metal with IPMI, and can put DDoS capacity and latency commitments into a contract.

Two things to settle before you order anything, from anyone. First, which jurisdiction your licence sits in and whether it requires data to stay inside a specific country; AVA Hosting's pages do not state a location, and two third-party write-ups place the facility in Moldova, so confirm it directly if residency is a constraint. Second, whether you need out-of-band console access. A VPS gives you root, not IPMI, and the difference only becomes obvious the day a box will not boot.

👉 [Start with the €10 Basic plan and upgrade later if the database grows](https://my.ava.hosting/aff.php?aff=15562)
