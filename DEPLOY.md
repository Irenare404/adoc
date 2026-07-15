# AusDungeon Documentation Site

`docs-site` is an independent, static GitHub Pages repository. It does not need the AusDungeon plugin source repository to deploy.

## Repository

The configured remote repository is:

```text
https://github.com/Irenare404/adoc.git
```

The repository includes its own GitHub Pages workflow at `.github/workflows/pages.yml`.

## Deploy

Push the `main` branch:

```powershell
git add .
git commit -m "Update AusDungeon documentation"
git push
```

In GitHub, open **Settings > Pages** and select **GitHub Actions** as the source. The workflow deploys the repository root as the static site.

## Custom Domain

`CNAME` is configured with:

```text
adoc.thispy.top
```

Create this DNS record:

```text
Type: CNAME
Host: adoc
Value: Irenare404.github.io
```

Then set `adoc.thispy.top` under **Settings > Pages > Custom domain** and enable HTTPS after GitHub verifies the domain.
