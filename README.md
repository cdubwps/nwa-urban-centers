# NWA Urban Centers

An interactive map identifying major urban centers and urban cores across Northwest Arkansas using Census tract population and workplace-job density.

**[View the interactive map](https://cdubwps.github.io/nwa-urban-centers/)**

## Overview

NWA Urban Centers analyzes **Benton and Washington Counties** to identify places where residents and workplace jobs are unusually concentrated.

Rather than using city limits or predefined neighborhood boundaries, the map uses **Census tracts** as its geographic building blocks. Each tract is evaluated using its population and the number of jobs located there.

The result is a map of connected high-activity areas, along with smaller secondary activity centers.

This is an independent data visualization and is **not an official Census, municipal, planning, zoning, or neighborhood designation**.

---

## Methodology

### Activity density

Each tract is assigned an **activity density**:

> **Activity density = (population + workplace jobs) ÷ tract land area**

The result is expressed as residents and workplace jobs per square mile.

Population comes from the **2023 ACS 5-Year Estimates**. Workplace employment comes from the **2023 LEHD Origin-Destination Employment Statistics (LODES) Workplace Area Characteristics dataset**, using **S000 (all jobs)** and **JT00 (all job types)**.

Workplace jobs represent jobs located in the tract, not where the workers live.

### Urban Centers

An **Urban Center** is a connected group of at least **two adjacent Census tracts** with activity density at or above the **80th percentile** of the study area.

### Urban Cores

An **Urban Core** is the highest-density portion of an Urban Center. It consists of connected tracts at or above the **95th percentile**, also requiring at least two adjacent qualifying tracts.

Core tracts are a subset of their corresponding Urban Center.

### Secondary Centers

A **Secondary Center** is an individual tract that:

* has activity density of at least **3,700 per square mile**,
* is adjacent to an Urban Center or Urban Core, and
* is not already part of an Urban Center.

Secondary Centers do not have a two-tract minimum.

The 3,700 threshold was chosen to capture smaller high-density nodes that fall below the primary Urban Center threshold.

---

## Why percentiles?

There is no universal density threshold that defines an urban center across every region.

Using the 80th and 95th percentiles makes the primary classifications relative to **Northwest Arkansas's own activity-density distribution**:

* **80th percentile:** unusually high activity density
* **95th percentile:** exceptionally high activity density

This allows the map to highlight the strongest concentrations within NWA without treating a particular density value as a universal definition of urbanity.

---

## Data

The analysis currently uses:

* **2023 ACS 5-Year Estimates** — Census tract population
* **2023 LEHD/LODES WAC** — workplace jobs
* **2023 Census TIGER/Line** — tract boundaries
* **Benton and Washington Counties** — 111 Census tracts total

The map combines these datasets in the browser to calculate activity density and identify connected centers.

---

## Limitations

This is a **tract-level density analysis**, so it does not capture every local variation in urban form.

In particular:

* Census tracts can contain areas with very different land uses.
* A dense development within a relatively large tract may be diluted by lower-density land elsewhere in the same tract.
* Workplace jobs are not the same as the number of people physically present at a given time.
* Density alone does not measure walkability, building form, transit access, land-use mix, or development quality.
* Changing the thresholds or underlying data would change the resulting centers.

The map should therefore be read as a visualization of **concentrated population and employment activity**, rather than a definitive map of urbanity.

---

## Technology

Built with:

* HTML
* CSS
* JavaScript
* Leaflet
* Turf.js
* Census data
* ArcGIS REST services
* OpenStreetMap
* GitHub Pages

The map runs entirely in the browser and does not require a backend server.

---

## Sources

* **U.S. Census Bureau — American Community Survey:** https://www.census.gov/programs-surveys/acs
* **U.S. Census Bureau — TIGER/Line:** https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html
* **U.S. Census Bureau — LEHD/LODES:** https://lehd.ces.census.gov/data/
* **OpenStreetMap:** https://www.openstreetmap.org/
* **Leaflet:** https://leafletjs.com/
* **Turf.js:** https://turfjs.org/

## License

This project is intended as a free public data-visualization project.

The underlying government datasets are provided by their respective public agencies and remain subject to their applicable terms of use.
