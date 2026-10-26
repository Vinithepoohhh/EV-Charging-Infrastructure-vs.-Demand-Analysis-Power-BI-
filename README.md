# EV-Charging-Infrastructure-vs.-Demand-Analysis-Power-BI-
Power BI dashboard comparing EV charging infrastructure with commercial BEV registrations by German ZIP code.

An interactive Power BI dashboard that compares public EV charging infrastructure with likely demand at ZIP code (PLZ) level in Germany. It helps identify which regions are most promising for new charging stations and where supply and demand don't match.

## Business question

Where should a charging provider expand next? Which ZIP codes have many commercial electric vehicles but little or no (fast) charging infrastructure?

## Features

- **Charging points by power class:** number of charging points at 22 kW and 150 kW for any ZIP code
- **Supply vs. demand:** commercially registered battery electric vehicles (BEV) shown next to charging points
- **Interactive map:** ZIP code locations on a map, filterable by power class and charging-point range
- **Coverage gaps:** indicator for ZIP codes with no charging points
- **Filters:** ZIP code slicer, charging-point range buckets and power-level filter

## Dashboard pages

| Page | Content |
|---|---|
| Ladepunkte | Charging points per ZIP code (22 kW and 150 kW), KPI cards, commercial BEV comparison table |
| Ladesäulen-Karte | Interactive map of charging stations with ZIP code, power and range filters |

## Data

Two public datasets were provided for this task:

1. **Charging station register** (Bundesnetzagentur): location, ZIP code and rated power (Nennleistung) of each charging point
2. **Vehicle registration statistics** (KBA), table **FZ 27.16**: commercial keepers, of which electric (BEV), by ZIP code

The raw files are not included in this repository. Place them in a `data/` folder and update the source paths in Power Query.

## Data model

| Table | Purpose |
|---|---|
| `Ladesaeulen` | Cleaned charging station register |
| `FZ27_16` | Commercial BEV registrations per ZIP code |
| `Ladesaeulen_PLZ_Summary_Final` | ZIP-level summary joined to both sources |

Main measures: `Anzahl_PLZ_22kW`, `Anzahl_PLZ_150kW`, `Total_Ladepunkte`, `BEV_gewerblich`, `Null Ladepunkte`

## Key findings

- The combined view shows which ZIP codes are the most promising targets for new charging stations.
- Some regions have many commercial BEVs but few charging points, especially fast chargers (150 kW). Others are already well covered relative to demand.
- Fast and normal charging show different coverage patterns in the same region, so both should be analysed together.

## How to use

1. Open `moonpowertask.pbix` in Power BI Desktop.
2. If prompted, point the data sources to your local copies of the two datasets.
3. Use the ZIP code slicer and filters to explore a region, or switch to the map page for a spatial view.

## Tools

Power BI Desktop, Power Query, DAX

## Author

www.linkedin.com/in/vinit-yadav69


