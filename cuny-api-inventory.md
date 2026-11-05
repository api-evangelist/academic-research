---
layout: doc
title: CUNY API Inventory
kicker: A first pass by API Evangelist
lead: What the City University of New York already publishes as APIs, across its 26 campuses, research centers and shared systems. It was compiled for Ryan Geftman-Gold on November 4, 2026.
noindex: true
permalink: /cuny-api-inventory/
---

The bar for this inventory is deliberately low: **anything published as an API counts**, official or not. These are the building blocks the [APIs for Academic Research](/) playbook aims to amplify and evolve.

**How it was compiled:**
- Searches across CUNY-wide systems, the 11 senior colleges, the 7 community colleges, Macaulay and SPS, and the graduate and professional schools.
- A sweep of 891 `*.cuny.edu` hostnames from public certificate logs.
- Checks of GitHub, Hugging Face, Zenodo, re3data, ROR and OpenAlex.

Every entry was checked live on November 4, 2026, using read-only requests, unless it's marked *unverified*.

## At a glance

- **AI and developer APIs.** CUNY is ahead of most universities here. The CUNY AI Lab publishes a model API, an MCP server and open-source client libraries.
- **Open data APIs.** CUNY publishes enrollment, retention and graduation, programs, degrees and campus data through New York's open data portal.
- **Scholarship APIs.** Academic Works exposes every campus's scholarship, and Manifold has an open API for publications.
- **The gaps.** There's no single place that lists any of this, and almost nothing exposes **research data** as an API. The research centers and archives publish tools and data with no API behind them.

## 1. AI and developer APIs

| What | Unit | Kind | Access | Evidence |
|---|---|---|---|---|
| [CAIL Model API](https://ailab.gc.cuny.edu/docs/api-keys/): OpenAI-compatible model listing and chat completions, plus a [model registry](https://ailab.gc.cuny.edu/models) and a sandbox | CUNY AI Lab (Graduate Center) | REST | Personal key after CUNY sign-in | Docs and registry are live. *The base URL is shown only after sign-in and is unverified.* |
| Kale Deploy MCP server | CUNY AI Lab | MCP (remote, OAuth) | Sign-in, scope `cail:deploy` | The endpoint answers with a standard OAuth challenge, and its protected-resource metadata is published. Schemas are in [cail-deploy](https://github.com/CUNY-AI-Lab/cail-deploy) |
| [CUNY AI Lab on GitHub](https://github.com/CUNY-AI-Lab): 47 repositories, including client, identity and sandbox libraries and an npm package | CUNY AI Lab | Source code and SDKs | Open | Live |
| Brightspace Valence API | CUNY-wide learning management system | REST | OAuth2 / app key | `brightspace.cuny.edu/d2l/api/versions/` returns version JSON |
| [Apps@CCNY](https://apps.ccny.cuny.edu/): "a PHP framework and API to … build and maintain apps that use CCNY's data sources" | City College | Internal API | Sign-in | Live |

## 2. Open data APIs

| What | Unit | Kind | Access | Evidence |
|---|---|---|---|---|
| Eight CUNY datasets on [NY Open Data](https://data.ny.gov/): campus locations, enrollment, retention and graduation, programs, degrees, employee headcount | CUNY | Socrata SODA REST | Open | For example, [retention and graduation](https://data.ny.gov/resource/ba86-tr5c.json) returns JSON |
| CUNY Service Corps and "Community Connect: Bronx" datasets on [NYC Open Data](https://opendata.cityofnewyork.us/) | Lehman College / CUNY Service Corps | Socrata SODA REST | Open | Listed in the NYC catalog API |

## 3. Research and scholarship APIs

| What | Unit | Kind | Access | Evidence |
|---|---|---|---|---|
| [CUNY Academic Works](https://academicworks.cuny.edu/): one repository with a set per campus. It includes Graduate Center dissertations, Public Health theses, the CUNY Law Review, Labor and Urban Studies, Macaulay, BMCC bulletins, Bronx yearbooks and finding aids, Hostos journals, LaGuardia archives, open course materials and Brooklyn College galleries | CUNY Libraries | OAI-PMH | Open | [ListSets](https://academicworks.cuny.edu/do/oai/?verb=ListSets) returns XML |
| [CUNY Manifold](https://cuny.manifoldapp.org/): open digital publications and course texts, including community-college editions | Graduate Center | JSON:API | Open | [Projects](https://cuny.manifoldapp.org/api/v1/projects) returns JSON |
| Library systems (Ex Libris Alma REST and Primo) | Office of Library Services | REST (vendor) | Key issued by OLS; Primo limited to CUNY IP addresses | [Alma](https://ols-support.cuny.edu/systems/alma/api), [Primo](https://ols-support.cuny.edu/systems/primo/apis) |
| CUNY in the scholarly registries: Crossref (485 DOIs), ROR (CUNY plus 24 child records), OpenAlex | Described by third parties | REST | Open | [Crossref member 14919](https://api.crossref.org/members/14919) |

## 4. Website content APIs

Open WordPress JSON APIs, which serve web pages and posts rather than research data:
- **Central and the Graduate Center:** [CUNY](https://www.cuny.edu/wp-json/) and the [Advanced Science Research Center](https://asrc.gc.cuny.edu/wp-json/).
- **Senior colleges:** [City Tech OpenLab](https://openlab.citytech.cuny.edu/wp-json/), Baruch, Brooklyn, Queens, Medgar Evers.
- **Community colleges and Macaulay:** BMCC, LaGuardia, Bronx, Guttman, Macaulay.
- **Graduate and professional schools:** Public Health (including the [Urban Food Policy Institute](https://www.cunyurbanfoodpolicy.org/wp-json/)), the School of Law, Labor and Urban Studies.
- **Research centers:** John Jay's [Data Collaborative for Justice](https://datacollaborativeforjustice.org/wp-json/).

## 5. Probably has an API, but it isn't reachable (unverified)

- **ArchivesSpace** at Baruch, Staten Island, the Graduate Center library, Hunter (Centro), Brooklyn, Kingsborough and Medgar Evers, and the CUNY archives. All refuse automated requests.
- **The CUNY Academic Commons**, which runs on WordPress and BuddyPress. It sits behind a captcha.
- **The CUNY Digital History Archive**, which runs on Omeka. It sits behind a bot check.
- **A Graduate Center New Media Lab archive** on Omeka S. It answers `"API is disabled"`.
- **A GitLab at the School of Professional Studies** and **the CUNY HPC Center.** Neither could be reached.

## 6. Public data tools with no API yet

These are the strongest candidates for the playbook. Each one already publishes valuable data to people, but not to software.

- **Center for Urban Research (Graduate Center):** [Redistricting & You](https://redistrictingandyou.org/), the [CUNY Mapping Service](https://www.urbanresearchmaps.org/), and the [Census 2020 Hard to Count Map](https://www.censushardtocountmaps2020.us/).
- **Newmark Graduate School of Journalism:** the community and ethnic media maps for NYC, New York State and LGBTQ media.
- **LaGuardia & Wagner Archives** (LaGuardia Community College).
- **Dominican Studies Institute library database** (City College).

## 7. Open source and community-built

- **Graduate Center open source:**
  - [Commons In A Box](https://github.com/cuny-academic-commons/commons-in-a-box) and 39 other repositories from the CUNY Academic Commons.
  - [GC Digital Fellows](https://github.com/GCDigitalFellows), 73 repositories of data and API workshops.
  - [Manifold](https://github.com/ManifoldScholar).
- **Built by students:** at least five unofficial CUNYfirst APIs, such as [CUNYSuite/CunyFirstAPI](https://github.com/CUNYSuite/CunyFirstAPI) and [QuaziH/CUNYfirst-API](https://github.com/QuaziH/CUNYfirst-API), plus bootcamp APIs from BMCC. This is clear demand for data CUNY doesn't yet serve.
- **On GitHub:** 177 organizations match "cuny", including CUNY Libraries, the CUNY AI Lab, the Journalism School and Public Health. None publishes an OpenAPI, GraphQL or MCP specification yet.
- **Hugging Face:** an organization named for the City College of New York exists. *It's unverified as official.*

## Not found

- **No front door:** there's no university-wide developer portal or API catalog.
- **No research data:** nothing from the Advanced Science Research Center or its core facilities.
- **No other API technologies** anywhere probed: no IIIF, SPARQL, GraphQL, Dataverse, CKAN, GeoServer or `llms.txt`.

## What this suggests

CUNY has more APIs than it appears to. The first step costs little: one public page that lists what's here, with machine-readable descriptions, so other researchers, developers and AI agents can find it. After that, the work is the playbook itself. Assess the research data and tools in sections 5 and 6, then pilot the first research API.

*Compiled by [Kin Lane](https://apievangelist.com/about/kin-lane/), API Evangelist. This is a first pass, so corrections and additions are welcome at [kin@apievangelist.com](mailto:kin@apievangelist.com).*
