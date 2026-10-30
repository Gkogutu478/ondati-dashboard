# Ondati Strategic Plan Implementation Dashboard

A web dashboard for tracking the Ondati Community Development Initiative Strategic Plan, November 2026 to October 2031. It shows budget, progress, timeline, results and risks for all 93 activities in the implementation matrix.

The dashboard reads its data from the Excel workbook in `data/`. You keep updating progress in Excel, and the dashboard follows.

## What is in this repository

| Path | Purpose |
| --- | --- |
| `index.html` | The dashboard page |
| `data.js` | Dashboard data, generated from the workbook. Do not edit by hand |
| `data/Ondati_Implementation_Matrix_2026-2031.xlsx` | The implementation matrix workbook (the single source of truth) |
| `scripts/build_data.py` | Converts the workbook into `data.js` |
| `.github/workflows/update-dashboard.yml` | Rebuilds `data.js` automatically when the workbook changes |

## Publish with GitHub Pages (one time)

1. In the repository on GitHub, open **Settings > Pages**.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose the **main** branch and the **/ (root)** folder, then **Save**.
3. After a minute or two the dashboard is live at `https://<your-username>.github.io/<repository-name>/`.
4. Open **Settings > Actions > General > Workflow permissions** and choose **Read and write permissions**, so the update workflow can save the refreshed data.

GitHub Pages on a free account requires a public repository, so the dashboard and workbook will be visible to anyone with the link.

## Update progress

1. Open the workbook, update **Status**, **% complete**, **Actual completion date** and **Remarks** on the Implementation Matrix sheet (and the Results Framework and Risk Register sheets as needed). Save it in Excel.
2. On GitHub, open the `data` folder, choose **Add file > Upload files**, upload the saved workbook with the same file name, and commit.
3. The **Update dashboard data** workflow rebuilds `data.js` within a minute; the live dashboard updates shortly after.

Changing quantities or unit rates on the Cost Estimates sheet updates the budgets the same way.

To rebuild locally instead: `pip install openpyxl` then `python scripts/build_data.py`, and commit `data.js`.

## Notes

- Budgets are indicative estimates (2026 prices plus contingency and escalation) and should be validated by a quantity surveyor.
- Save the workbook in Excel or LibreOffice before uploading, so calculated budgets are stored in the file.

*Gini Nyalore.*
