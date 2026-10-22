# Run the renovation example

This is a source-based reproduction guide. Rhino, simulation tools and optimization were not executed during migration; it does not establish numerical reproducibility.

## Environment

The original README specifies Ladybug Tools **1.5.0** and Colibri **2.0.0**. Use them within Rhino/Grasshopper with a legacy GhPython runtime compatible with the Python 2 helper. Honeybee Energy, OpenStudio and EnergyPlus are required by the described workflow. **TODO:** record their exact versions, the Rhino/GhPython version, operating system, full plugin set and any solver/iteration settings after a successful run. A generic Python 3 `requirements.txt` cannot describe this graphical environment.

## Graphical steps

1. Open Rhino and choose **File → Open → `plan.3dm`** from the checkout. Start Grasshopper and choose **File → Open → `230502_Wallacei_packages.gh`**.
2. Keep simulation and Colibri iteration disabled while inspecting the canvas. Resolve missing-plugin messages and reconnect any Rhino geometry references to the intended objects in the bundled plan. Inspect the resulting zones, surfaces and units before running an analysis.
3. In the file-input group shown in the [original guide](original-readme.md), set the material input to the checkout's `mat_DB4.csv`, construction input to `construction_DB.csv`, and weather input to `Uddevalla2017EPWv2.epw`. Replace stored absolute paths with the actual checkout paths.
4. Inspect the existing-building Honeybee materials and the package-combination group. The helper expects `mat_DB`, `cons_DB`, `base_Wall`, `base_Floor`, `base_Roof` and `base_Window`; verify that all referenced materials and constructions resolve.
5. Review the definition's EnergyPlus/OpenStudio simulation settings, carbon/cost assumptions and output directories. Point generated files to a local working directory outside the tracked inputs. Run one selected package before starting a full enumeration, and inspect simulation warnings and errors.
6. After the single case is usable, enable the Colibri iteration described in the original guide. Record the selected domain, iteration settings, software versions and all changed input values alongside the generated CSV. **TODO:** record exact canvas control labels, iteration limits and run duration after a project-member run.
7. Inspect the exported heating, carbon and cost fields in a CSV viewer or the DesignExplorer workflow linked in the original guide. Screenshot references in `Design_explorer.csv` refer to case images that are not included in this checkout.

## Expected outputs and checks

| Item | Check |
| --- | --- |
| Honeybee constructions | Every construction UUID resolves; layer order and base-material composition match the intended package. |
| Single-case energy simulation | Model geometry and weather location are appropriate; inspect the actual EnergyPlus errors and the heating result's units. |
| Iteration CSV | Contains one row per completed case with the requested package/input choice and heating, LCA and LCC outputs. |
| Historical `Design_explorer.csv` | Preserved example with headers `in:Octopus slider`, `out:Heating (kWh)`, `out:LCA (C02e/m2)`, `out:LCC (SEK/m2)`, `img`. It is not a verified regression baseline. |

The source screenshots show construction and operational contributions and a DesignExplorer result view. They do not document all analysis-period, economic or emissions assumptions. Exact agreement with the historical CSV cannot be promised until those settings, tool versions and original run conditions are confirmed. No randomized algorithm settings or seeds are documented in the README; inspect the definition before reporting optimization reproducibility.

See [data provenance](../data/README.md) for input origins, units and missing reuse information. Preserve the original example results when conducting new runs.
