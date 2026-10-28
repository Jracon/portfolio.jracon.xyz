+++
description = 'Software engineer: backend APIs, data pipelines, and geospatial/ML for research.'
aliases = ['/resume']
+++

I'm Jade Meskill, a software engineer with 2+ years of experience building backend APIs and data pipelines for government-funded research in [global supply chains](https://fewsion.us) and [U.S. water resources](https://water.usgs.gov/wrri/grant-details.php?ProjectID=2023AZ001G&Type=National); experienced with geospatial data science, graph databases, high-performance computing, and applied machine learning. Open to relocation.

## Work Experience

### Research Software Engineer @ Northern Arizona University

_Jan 2025 - Nov 2026_

**USGS Water Accounts**: technical lead on [_Developing the Next Generation of U.S. Water Accounts_](https://water.usgs.gov/wrri/grant-details.php?ProjectID=2023AZ001G&Type=National), a USGS [104(g) National Competitive Grant](https://wrrc.arizona.edu/news/nau-research-project-receives-federal-104g-grant) (2024-2026).

- Developed datasets and algorithms for 5 hydrology and machine learning manuscripts (1 under review, 4 in preparation).
  - Adapted a co-training CNN and random forest pipeline to downscale watershed water use totals to 1 km CONUS rasters across 4 water use sectors (**GPU Keras/TensorFlow**, **scikit-learn**, **SLURM**).
    - Cut compute time ~7.5× (5 h to ~40 min per raster layer) with vectorized raster operations and prediction masking.
    - Diagnosed and fixed a mis-scaled loss function that was degrading model accuracy.
  - Extended water resource dependency equations to CONUS with a watershed flow graph (**GeoPandas**, **rasterio**).
- Co-planned project phases and coordinated 6 undergraduate researchers building CONUS water use datasets as inputs to System of Environmental-Economic Accounting (SEEA) water accounts.

**FEWSION Supply Chain Database**

- Designed a provenance-based consensus system for merging conflicting facility records from separate data providers, with per-field lineage, confidence, and trust-weighted consensus functions (**PyNest**, **MongoDB/beanie**, **Azure Cosmos DB**).
  - Synced consensus records from **MongoDB** into **PostgreSQL** for spatial queries.
- Developed an entity-resolution matcher to link incoming records to existing facilities, avoiding duplicates and scoring candidates on industry code, facility type, fuzzy name similarity, and distance (**H3**, async **SQLAlchemy**).
- Built **Azure Functions** ingestion pipelines for millions of records across economic sectors worldwide: Premise field surveys, Overture Maps (**DuckDB**), OpenStreetMap infrastructure, and global ports of entry (land, sea, and air).
- Migrated the generic CRUD API layer to high-availability **PyNest** services and async **SQLAlchemy**.
- Authored an internal library of parameterized **Cypher** queries in **Neo4j** to feed [an economic network visualization](https://www.fewview.us/) with multi-hop trade flow metrics and trade relationship resilience.

### Research Intern @ Northern Arizona University

_Jan 2024 - Dec 2024_

**USGS Water Accounts**

- Modeled environmental flow requirements for ecosystems across the Potomac River Basin for a [high-resolution water tower model](https://doi.org/10.22541/essoar.15006823/v1), through kriging interpolation of USGS stream gauge records (**PyKrige**).
- Developed a [mass-preserving spatial disaggregation pipeline](https://github.com/Sjostedt-eric/usgs_disaggregation/tree/thermoelectric/thermoelectric) for monthly CONUS thermoelectric power plant water use, allocating each plant's consumption and withdrawal by building footprint area (**GeoPandas**, **Shapely**, **rasterio**, **Overpass API**).

**FEWSION Supply Chain Database**

- Built a **MongoDB** REST API using **beanie** and an accompanying pipeline to preprocess Overture Maps data into provenance-tracked data sources.
- Designed a generic CRUD and routing layer for a **FastAPI** + **SQLAlchemy/GeoAlchemy2** REST API over **PostGIS**, with spatial and AND/OR filtering and **pytest**.
- Implemented a global boundary reconciliation algorithm (**GeoPandas**, **Shapely**) that detects slivers where national and subnational boundaries fail to nest and merges them into neighbors.

### Student Support Technician @ Northern Arizona University

_Aug 2021 - Dec 2024_

- Resolved over 4,500 call and email tickets campus-wide across identity management, email, and software licensing.

### IT Specialist @ D2 Surveying

_Oct 2020 - Oct 2021_

- Bootstrapped a **FreeBSD** FTP server for field file transfer.
- Deployed a peer-to-peer **Syncthing** network for office collaboration.
- Wrote **Python** and **VBA** Excel automations to organize customer and geospatial data.

## Projects

### genixis

A [**Nix** flake for declarative homelab and development infrastructure](https://github.com/Jracon/genixis) across macOS, WSL, and NixOS machines.

- **Reproducible hosts**: one set of modules builds every machine; per-machine settings stay out of the repo, and **disko** handles partitioning. Configured machines can be rebuilt with a single command.
- **Self-hosted services**: **Podman** containers for a Git forge (Forgejo), a Matrix homeserver, a password manager, and a media stack; exposed through **Caddy** and **Tailscale**, with **agenix**-encrypted repo secrets.
- **CI**: a nightly **Forgejo Actions** job on a self-hosted runner updates all inputs, checks formatting, then evaluates and builds every configuration in the Nix sandbox.
- **Agent workflow**: per-branch git worktrees for running parallel agents in one repository. Context, skills, and memory are version-controlled and generated from the same flake.

## Education

**Bachelor of Science** in **Applied Computer Science** @ Northern Arizona University (Flagstaff, Arizona), graduated Dec 2024, GPA 3.67

## Publications

- Sjöstedt, E. C., **Meskill, J. I.**, Kearns, M., Rushforth, R. R., & Zegre, N. P. (2026). _Basin-Scale Water Towers: Insights from Comparing High-Resolution Water Tower Models of the Potomac River Basin, USA_. Under review; preprint on ESS Open Archive. [doi:10.22541/essoar.15006823/v1](https://doi.org/10.22541/essoar.15006823/v1)

## Skills

- **Languages**: Python, SQL, Cypher, Nix, Bash, VBA
- **Backend & APIs**: FastAPI, REST, Pydantic, SQLAlchemy (async), GeoAlchemy2, beanie, PyNest, psycopg2, pytest
- **Databases**: PostgreSQL/PostGIS, MongoDB, Azure CosmosDB, Neo4j, DuckDB
- **Data & ML**: ETL pipelines, entity resolution, fuzzy matching, pandas, NumPy, scikit-learn, Keras, TensorFlow, Matplotlib, Jupyter
- **Geospatial**: GeoPandas, Shapely, rasterio, H3, OpenStreetMap/Overpass API, spatial disaggregation, ordinary kriging (PyKrige)
- **Infrastructure**: Linux, FreeBSD, Git, Nix Flakes, NixOS, nix-darwin, Home Manager, disko, agenix, Docker/Docker Compose, Podman, Proxmox, Caddy, Tailscale, CI/CD (Forgejo Actions), Azure (Functions, Blob Storage), HPC, SLURM, GPU computing
- **AI tools**: Claude Code, parallel agentic development workflows
