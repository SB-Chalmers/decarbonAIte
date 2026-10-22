# Workflow, assumptions and limitations

## Method

The preserved workflow generates a building model from a Rhino plan, combines existing Honeybee constructions with renovation packages, simulates heating demand through EnergyPlus, and calculates construction and operational contributions to carbon and cost. Colibri iterates the design domain and exports results for DesignExplorer. The [original workflow guide](original-readme.md) provides the original schema examples and screenshots.

[`HB_combinematerials.py`](../HB_combinematerials.py) reads material rows keyed by `UUID` and construction rows grouped by element and identifier. It builds wall, floor and roof packages by appending listed layers to the relevant base construction. Window alternatives use Honeybee simple glazing materials. Base wall, floor, roof and window objects are supplied by the Grasshopper definition.

## Input formats

- `mat_DB4.csv`: `UUID,Material,Thickness,Conductivity,Cost,Embodied carbon,Density,U-value`.
- `construction_DB.csv`: `Element,Identifier,Layer,UUID`. Each material reference must exist in the material database. The helper appends layers in CSV row order; it does not sort them by the `Layer` field.
- `plan.3dm`: the Rhino plan used by the graphical workflow.
- `Uddevalla2017EPWv2.epw`: bundled EPW weather input. Its filename alone does not establish its production method or reuse terms; see [data provenance](../data/README.md).

The source uses thickness in metres, conductivity in W/m-K, density in kg/m³, and glazing U-value in W/m²K. Cost and embodied-carbon reference quantities and life cycle boundaries need confirmation before adapting the CSV values to another study.

## Preserved assumptions and runtime limits

Opaque package materials use fixed specific heat of 950 J/kg-K, `MediumRough` roughness, and thermal/solar/visible absorptances of 0.9/0.7/0.9. Simple glazing uses fixed solar heat gain coefficient 0.3 and visible transmittance 0.6. These are assumptions in the original source, not validated material-specific properties.

The source documents Ladybug Tools 1.5.0 and Colibri 2.0.0. The helper uses Python 2 `print` syntax and Grasshopper-supplied globals, so it is not a standalone Python 3 program. Exact Rhino/GhPython, OpenStudio and EnergyPlus versions, operating system and any additional plugins are **TODO**. The definition's filename contains “Wallacei”, while the README documents Colibri; a project member must confirm the complete plugin set from the running canvas.

No automated test suite is supplied. Numerical results, geometry references, simulation settings, output paths, iteration configuration, economic assumptions and emissions factors require inspection in the original definition. The migration changes documentation and repository boundaries, not scientific methods.

## Documentation and project metadata

- [Run and inspect the example](reproduce.md).
- [Data inventory and provenance](../data/README.md).
- [Migration and original-file manifest](migration.md).

Jacob Forsberg is the author named in the original README. **TODO:** confirm current maintenance status, additional authors and agreed roles, funding, thesis/paper links, and software/data archive identifiers. [CITATION.cff](../CITATION.cff) contains only verified named authorship and repository metadata.
