---
layout: doc
title: CUNY Research Data Ready for an API
title_suffix: CUNY Research Data Ready for an API
kicker: A first pass by API Evangelist
lead: The low-hanging fruit. These are CUNY research datasets and data tools already published for people, ready to be published as APIs for software, other researchers and AI agents. Compiled for Ryan Geftman-Gold on November 4, 2026.
noindex: true
permalink: /cuny-research-data-candidates/
---

This is the companion to the [CUNY API Inventory](/cuny-api-inventory/). That page lists what CUNY already publishes *as* an API. This one lists the research data CUNY publishes *without* one, ranked by how little work it would take to change that. These are the natural first assessments for the [APIs for Academic Research](/) playbook.

**How it was compiled:** five searches across the following, with every entry checked live using read-only requests on November 4, 2026:
- The Graduate Center's centers and institutes
- Health, food and justice research
- Science and environmental data at the senior colleges
- Archives and collections
- Datasets CUNY researchers have deposited in DataCite, Dataverse, Zenodo, Dryad and OpenAlex

Many CUNY sites block automated requests, so some promising units appear only in the "still to check" list.

**How each candidate is scored:**

| Score | Meaning |
|---|---|
| **5** | Already structured, public, kept up to date, with a clear audience. An API is mostly packaging. |
| **4** | Structured and public, but needs work on documentation, versioning or licensing. |
| **3** | Valuable, but needs cleanup or extraction first. |
| **2** | Small, static, or mostly prose. |

## At a glance

- **More research data than anyone would guess.** DataCite lists about **2,100 datasets** crediting the "City University of New York". OpenAlex links about 600 more to five CUNY institutions.
- **Data already published as files.** The best candidates are already public as CSVs, sensor feeds or structured tables behind a map or dashboard. They're one documented, versioned step from being an API.
- **Five strong first pilots:**
  - CCNY's NYC weather-station network
  - The CUNY Institute for Demographic Research's population and climate datasets
  - John Jay's justice dashboards
  - The Journalism School's community media directory
  - CCNY's air-quality archive

## Score 5: ready to pilot

### NY Urban Hydro-Meteorological Testbed (NY-uHMT)
**CCNY, NOAA Center for Earth System Sciences and Remote Sensing Technologies (CESSRST)**
- **The data:** about 21 weather stations across the five boroughs, at schools, public housing, the Queens Botanical Garden and a library. They record air temperature, humidity, rainfall and soil moisture every 15 minutes, going back to 2018.
- **Current form:** a [CSV file per station](https://datadb.noaacrest.org/public/uhmt/Processed_Data/), a [chart page](https://crest.cuny.edu/uhmt/data.html) and a station map. The server's own notes describe batch download by script, and an empty `json/` folder suggests an API was once planned.
- **Who'd use it:** emergency management, flood and heat researchers, city agencies, schools.
- **To confirm:** which stations are still reporting. One station's file ends in August 2024.

### Population, coastal and climate-migration datasets
**CUNY Institute for Demographic Research (CIDR), with Columbia's CIESIN and the World Bank**
- **The data:**
  - Low Elevation Coastal Zone urban and rural population and land area ([DVN/8QYAFZ](https://doi.org/10.7910/DVN/8QYAFZ))
  - Groundswell climate-migration projections ([DVN/JGJNP5](https://doi.org/10.7910/DVN/JGJNP5))
  - Global settlement points and urban extents ([DVN/RLOK0B](https://doi.org/10.7910/DVN/RLOK0B))
- **Current form:** versioned tabular, raster and geodata on Harvard Dataverse, republished in October 2026 across about seven records.
- **Who'd use it:** climate risk, development and humanitarian planning, and urban research worldwide.
- **Why it's ready:** one CUNY population and climate API could serve all of them, queried by country, scenario and year.

## Score 4: structured and public, needs packaging

| Candidate | Unit | The data | Current form | Who'd use it |
|---|---|---|---|---|
| [Data Collaborative for Justice dashboards](https://datacollaborativeforjustice.org/dashboard-sqf/) | John Jay College | About ten dashboards: stop-and-frisk rates by race and precinct, the [NYC jail population tracker](https://datacollaborativeforjustice.org/analytic-tools/the-new-york-city-jail-population-tracker/), criminal and civil summons, jail admissions by zip code, convictions by county, a marijuana policy timeline | Dashboards that load public CSV and GeoJSON files from the site. Not documented or versioned | Journalists, advocates, policy staff, researchers |
| Community & ethnic media directory ([NY State](https://nysmap.journalism.cuny.edu), [AAPI](https://amimap.journalism.cuny.edu)) | Newmark Graduate School of Journalism, Center for Community Media | Outlets by language, community and location | Interactive maps backed by structured Airtable tables | Advertisers and city agencies (NYC buys ads in community media), journalists |
| [Optical Remote Sensing Lab archive](https://datadb.noaacrest.org/public/ORSL/) | CCNY, CESSRST | NO2 (still being updated), ozone, CO2, PM2.5, ceilometer and lidar boundary layer, microwave radiometer | Directory of text files | Satellite validation, air-quality and environmental-justice work |
| [Redistricting & You](https://www.redistrictingandyou.org/) | Graduate Center, Center for Urban Research | New York and US district plans compared, with demographics by district | Map app built on structured geodata | Journalists, civic groups, campaigns |
| [Census Hard to Count Map](https://www.censushardtocountmaps2020.us/) | Graduate Center, Center for Urban Research | Hard-to-count scores and self-response rates by census tract, nationwide | Interactive map. It has a 2030 planning successor | Census outreach, foundations, local government |
| East Coast cyclone, storm-blocking and storm-surge series ([DVN/MBPPHW](https://doi.org/10.7910/DVN/MBPPHW) and three more) | CCNY (James Booth) | Extreme-weather and surge time series | Tabular files on Dataverse | Climate and coastal-risk research |
| Seabird survey series (for example [10.82144/75412923](https://doi.org/10.82144/75412923)) | College of Staten Island (Richard Veit) | About 25 survey datasets from Atlantic cruises, 2006–2012, in one consistent format, CC0 | Records on OBIS-SEAMAP | Ocean biodiversity research |
| [BDNYC brown dwarf database](https://doi.org/10.5281/zenodo.629242) | BDNYC (AMNH and CUNY) | Brown dwarf observations | SQLite database on Zenodo | Astronomy |

## Score 3: valuable, needs extraction or cleanup

- [**Latino Data Project**](https://clacls.gc.cuny.edu/latino-data-project/) (Graduate Center, CLACLS): dozens of reports on NYC and US Latino demographics, poverty, health and education. They're published as PDFs and web pages, but built from public census microdata, so the tables could be regenerated as data.
- [**LaGuardia & Wagner Archives**](https://laguardiawagnerarchive.lagcc.cuny.edu) (LaGuardia Community College): NYC mayoral papers and photographs behind a search page.
- [**CUNY Digital History Archive**](https://cdha.cuny.edu): documents, photos and oral histories of CUNY. It probably runs on Omeka, which has a built-in API, but the site sits behind a bot check.
- **CCNY research datasets on Zenodo:** [ClimKern](https://doi.org/10.5281/zenodo.10223376), climate-feedback kernels with a companion Python package; and the [WAD2M global wetland area dataset](https://doi.org/10.5281/zenodo.3998453), CUNY's most-cited dataset in OpenAlex.
- [**CHASING COVID cohort study**](https://doi.org/10.5281/zenodo.6127734) (CUNY School of Public Health): national public-health cohort data.
- **Smaller record-level collections:** the [Slave Registry of Mayagüez, Puerto Rico, 1872](https://doi.org/10.7910/DVN/QHZQLT), [Fox and CNN coding data, 2010–2020](https://doi.org/10.7910/DVN/ULBATX), and the [DROP Drosophila parasitoid reference database](https://doi.org/10.5281/zenodo.4519656).
- [**WRF precipitation forecasts for Puerto Rico**](https://datadb.noaacrest.org/public/wrf-pr/archives/) (CCNY CESSRST): current, but published only as images. An API would need the underlying model output.
- [**CESSRST data products catalog**](https://www.cessrst.org/research/data-products/): an index of the center's products. Some links have gone stale.

## Score 2: small or mostly static

- [**Hall of Fame for Great Americans**](https://www.bcc.cuny.edu/about-bcc/history-architecture/hall-of-fame-for-great-americans/) (Bronx CC): 102 honorees, their busts and sculptors. It's small, but easy to turn into structured data, and has tourism and education value.
- [**NY Solar Map**](https://nysolarmap.com/) (Sustainable CUNY): rooftop solar potential. A backend route exists but isn't documented. It's worth asking the team.
- [**NYCdata**](https://www.baruch.cuny.edu/nycdata/) (Baruch, Weissman Center): NYC facts repackaged from other sources, some of them out of date.
- **John Jay Research & Evaluation Center data briefs**, the **Urban Food Policy Institute** reports, and **Healthy CUNY**: mostly prose and PDFs.

## Still to check in a browser

These looked promising but blocked automated access or didn't respond:
- **Hunter:** the NYC Food Policy Center (including its food policy indicators), Centro (the Center for Puerto Rican Studies) archives and data, the Center for Health Equity, the Brookdale Center for Healthy Aging.
- **The Graduate Center:** the Advanced Science Research Center's core facilities and datasets, the Stone Center on Socio-Economic Inequality, the Institute for State and Local Governance, the NYC Labor Market Information Service.
- **CCNY:** the Levich Institute, the Center for Water Resources, the Dominican Studies Institute.
- **University-wide:** the CUNY Institutional Research Data Book, the campus ArchivesSpace archives, the Building Performance Lab.
- **Queens College:** the Queens Memory Project.

## Suggested first pilots

1. **NY-uHMT weather stations.** The data, purpose and audience are already in place. An API, a station feed and a map embed would put hyperlocal NYC weather in front of emergency management, schools and app builders.
2. **CIDR population and climate.** One API over a widely used, CUNY-led global data series.
3. **Data Collaborative for Justice.** Document and version the files the dashboards already load, and publish them as an API.
4. **Community media directory.** Turn the Airtable directory into an open API that agencies and advertisers can build on.

Each of these would make a strong worked example for the playbook.

*Compiled by [Kin Lane](https://apievangelist.com/about/kin-lane/), API Evangelist. This is a first pass. Affiliations and licenses come from public records, and corrections and additions are welcome at [kin@apievangelist.com](mailto:kin@apievangelist.com).*
