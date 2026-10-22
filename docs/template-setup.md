# Set up a new research repository

Use **Use this template** on GitHub and create a repository with a short, lowercase, hyphenated name, such as `building-energy-study`. Give the project a readable title in `README.md`, such as **Building Energy Study**.

1. **Describe the project.** Replace every placeholder in `README.md`, `CITATION.cff`, `LICENSE`, `docs/reproduce.md`, and `data/README.md`. Explain the research context, aim, status, people, roles, and funding. Remove rows and sections that do not apply.
2. **Set the GitHub About panel.** Add a one-sentence description a non-specialist can understand. Add either `masters-thesis` or `phd-research`, followed by a few domain topics such as `renovation-planning`, `energy-simulation`, or `daylight` (plus other accurate topics). If the project belongs to Computational Sustainable Design, add `csd` as a topic. For another research group, ask your supervisor which group abbreviation to use.
3. **Fix the badges.** Show the actual primary language and version. Confirm the license badge matches the chosen license. Keep Zenodo and paper DOI badges marked **pending** until those identifiers exist; then link each badge to its own DOI. Replace the pending tests badge with the status badge of a real test workflow, or explain that no automated tests are available. Do not show a green tests badge for a workflow that does not test the project.
4. **Make the first run easy.** Name the required software, versions, input files, environment setup, and one exact command or short graphical procedure that works from a fresh checkout. Keep `requirements.txt` only for Python projects, or use a project-specific `environment.yml` if that captures the environment better. Include a small demo notebook if this repository is a tool.
5. **Keep data small in Git.** Commit code, configurations, documentation, and only small example inputs. Describe how generated data are recreated. Archive larger datasets on Zenodo and link the exact dataset record and version from `data/README.md`. State the data license separately from the code license.
6. **Prepare citations and release metadata.** Link the thesis record in DiVA or the Chalmers Master's thesis portal when available. Add author names and ORCIDs to `CITATION.cff`; add the paper DOI when a paper is published. Check the license and copyright holders with the supervisor, especially for funded or partner projects. Name the funder and grant number if any.
7. **Check the public view.** Read the README as a visitor, open every link, confirm that the instructions reproduce one result, and remove remaining placeholder text before treating the repository as a finished research output.

`AGENTS.md` contains instructions for an LLM asked to reorganize the project. Keep it at the repository root: this is the filename recognized by coding assistants, rather than `.agents.md`.

## Badge replacements

After a DOI exists, replace its pending badge with a DOI badge linked to the matching record. For example:

```markdown
[![Zenodo DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1234567.svg)](https://doi.org/10.5281/zenodo.1234567)
[![Paper DOI](https://img.shields.io/badge/DOI-10.0000%2Fexample-blue)](https://doi.org/10.0000/example)
```

Replace the example identifiers with real values. A paper DOI identifies the paper; a Zenodo DOI identifies the archived record. If you enable Zenodo's GitHub integration, connect the repository and archive a GitHub release to obtain a software record DOI. A separately deposited dataset has its own record and DOI.

When a real GitHub Actions test workflow named `tests.yml` exists, replace the pending badge with:

```markdown
[![Tests](https://github.com/OWNER/REPOSITORY/actions/workflows/tests.yml/badge.svg)](https://github.com/OWNER/REPOSITORY/actions/workflows/tests.yml)
```

Substitute the new repository owner and name. Keep the badge visible only while the workflow accurately tests the project.
