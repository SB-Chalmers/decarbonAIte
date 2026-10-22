# decarbonAIte

Explore building renovation packages using a Grasshopper workflow that combines energy simulation, life cycle assessment and life cycle costing.

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

This renovation workflow is associated with the [decarbonAIte research project](https://research.chalmers.se/en/project/10568), funded by VINNOVA (grant 2021-02759). See [research context, people and related work](docs/research-context.md).

The original documentation names **Jacob Forsberg** as author and is dated July 2023. The repository preserves the Grasshopper definition, Rhino plan, construction helper, example databases, weather file and example results from the Computational Sustainable Design collection. See [migration and provenance](docs/migration.md).

## Getting started

1. Use Rhino and Grasshopper with the source-documented **Ladybug Tools 1.5.0** and **Colibri 2.0.0**. Exact Rhino/OpenStudio/EnergyPlus versions and the full plugin set remain to be confirmed.
2. Open [`plan.3dm`](plan.3dm) in Rhino, then open [`230502_Wallacei_packages.gh`](230502_Wallacei_packages.gh) in Grasshopper.
3. Repoint the definition's file inputs to [`mat_DB4.csv`](mat_DB4.csv), [`construction_DB.csv`](construction_DB.csv), and [`Uddevalla2017EPWv2.epw`](Uddevalla2017EPWv2.epw). Inspect the model and warnings before enabling simulation or iteration.
4. Follow [the graphical reproduction procedure](docs/reproduce.md).

Read [methods and limitations](docs/README.md), [data provenance](data/README.md), and the [original workflow guide](docs/original-readme.md). Cite using [CITATION.cff](CITATION.cff). Repository code is licensed under [MIT](LICENSE).

The legacy workflow has not been executed during migration. Exact runtime versions, current software maintenance roles and archive identifiers remain **TODO** for the project members.
