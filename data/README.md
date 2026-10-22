# Data inventory and provenance

The small original example inputs and historical CSV are retained at repository root so the original definition's file layout remains recognizable. [The migration manifest](../migration.json) records original paths and checksums.

| File | Role | Source and interpretation |
| --- | --- | --- |
| `plan.3dm` | Rhino geometry input | Preserved project plan; coordinate system and intended model units need confirmation in Rhino. |
| `mat_DB4.csv` | Material input | Original example material/thermal/cost/carbon table. See [schema and assumptions](../docs/README.md). Material-data sources, cost year/currency basis and carbon reference quantities are **TODO**. |
| `construction_DB.csv` | Package input | Original example element/layer/UUID table referencing the material CSV. |
| `Uddevalla2017EPWv2.epw` | Weather input | Original bundled EPW. **TODO:** verify producer, station/period, preprocessing, applicable license and attribution; the filename does not establish them. |
| `Design_explorer.csv` | Historical generated result example | Original heating/LCA/LCC CSV. Original run configuration has not been reconstructed; referenced case images are not included. |
| `media/` | Documentation images | Preserved screenshots of input groups, simulation, calculations, iteration and visualization. |

Code is [MIT licensed](../LICENSE). External weather/material data and third-party software retain their original terms; **TODO:** record separate dataset/image terms and attribution where applicable. No data license, institutional permission or external archive has been inferred from the code license.

Generate new simulation outputs in a separate working directory and record inputs, versions and settings using [the reproduction guide](../docs/reproduce.md). Do not overwrite the historical example CSV with new runs. Larger simulation results should be archived separately when an appropriate archive is supplied.

**Dataset archive DOI:** not recorded in the source; TODO if an archive is created.
**Software archive DOI:** not recorded in the source; TODO if an archive is created.
