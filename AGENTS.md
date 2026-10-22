# Instructions for assistants

This repository documents a research project. Preserve scientific meaning and provenance while improving its organization. Read `README.md`, `docs/`, `data/README.md`, and `CITATION.cff` before moving files.

When asked to reorganize the project:

1. Inventory the current files and identify code, notebooks, inputs, generated outputs, documentation, and archived data. State any uncertain classification.
2. Keep the root README short. Put methods, assumptions, file formats, limitations, and reproduction details in `docs/`. Keep data provenance and archive links in `data/README.md`.
3. Move files only when their purpose is clear. Preserve original inputs, results, authorship, and citation information. Do not change scientific methods or numerical results merely to improve layout.
4. Prefer scripts and documented commands for regenerating data. Do not add large generated datasets to Git. Refer to an existing Zenodo record for large archived data; do not invent or publish a record.
5. Update imports, paths, links, and instructions affected by any move. Keep one small example or demo notebook if the project is a tool.
6. Treat people, roles, funding, licenses, publication status, DOI links, and test results as facts requiring evidence. Leave an explicit `TODO` when they cannot be verified; never fabricate them.
7. At the end, report what changed, how to run the project, what checks were actually performed, and what still needs a project member's input.

The human setup checklist is in `docs/template-setup.md`. Follow the user's task and any more specific instructions in the repository.
