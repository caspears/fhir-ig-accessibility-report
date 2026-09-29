# FHIR Implementation Guide Accessibility Remediation

This repository builds a navigable documentation site from the Markdown files
under `docs/`.

## Publish with GitHub Pages

1. Create an empty GitHub repository.
2. Upload all files and folders from this package to the repository root.
   Ensure `.github/workflows/publish-docs.yml` is included.
3. Commit the files to the `main` branch.
4. Open **Settings > Pages** in the GitHub repository.
5. Under **Build and deployment**, set **Source** to **GitHub Actions**.
6. Open **Actions** and wait for **Publish documentation** to complete.
7. Return to **Settings > Pages** for the published site address.

Future pushes to `main` automatically rebuild the site.

## Edit the report

- Report pages are Markdown files under `docs/`.
- The site title, page labels, and navigation order are in `mkdocs.yml`.
- Add a page to `docs/`, then add it to the `nav` section of `mkdocs.yml`.
- Run the **Publish documentation** workflow manually from the Actions tab if
  a rebuild is needed without a new commit.

## Preview locally (optional)

Local installation is not required for GitHub publication. To preview locally:

```shell
python -m pip install -r requirements.txt
mkdocs serve
```

OR Preview locally using an isolated environment
Run these commands from the project directory in PowerShell:
```shell
py -3.12 -m venv .venv
.\.venv\Scripts\python.exe -m pip install --upgrade pip
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m mkdocs serve
```

Open the address printed by MkDocs, normally `http://127.0.0.1:8000/`.

## Important status note

Verified color values are based on the supplied original and remediated CSS
and representative generated pages. Open findings and untested checklist
requirements remain explicitly identified; the site does not make a blanket
conformance claim.
