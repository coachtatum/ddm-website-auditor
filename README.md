# DDM Website Auditor

React website audit frontend for Digital Doorway Marketing.

## Deployment

This repository contains a GitHub Actions workflow at `.github/workflows/deploy-pages.yml` which builds the React frontend on each push to `main` and attempts to publish it through GitHub Pages.

To enable Pages: Repository **Settings > Pages > Build and deployment > GitHub Actions**.

Expected URL: https://coachtatum.github.io/ddm-website-auditor/

**Note:** GitHub Pages supports the React frontend only. Live website scanning requires separately hosting the Node.js API and configuring the repository Actions variable `VITE_API_BASE_URL` to point to it.
