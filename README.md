# DDM Website Auditor

React website audit frontend for Digital Doorway Marketing.

## Deployment

This repository contains a GitHub Actions workflow at `.github/workflows/deploy-pages.yml` which builds the React frontend on each push to `main` and attempts to publish it through GitHub Pages.

To enable Pages: Repository **Settings > Pages > Build and deployment > GitHub Actions**.

Expected URL: https://coachtatum.github.io/ddm-website-auditor/

**Note:** GitHub Pages supports the React frontend only. Live website scanning requires separately hosting the Node.js API and configuring the repository Actions variable `VITE_API_BASE_URL` to point to it.

## Deploy Node.js API

[Deploy backend to Render](https://render.com/deploy?repo=https://github.com/coachtatum/ddm-website-auditor)

After Render provisions the service, copy its public `https://...onrender.com` URL and add it to this repository's **Settings → Secrets and variables → Actions → Variables** as `VITE_API_BASE_URL`. Rerun the GitHub Pages workflow to build the frontend with the API URL.

The backend exposes `GET /health` and `POST /api/audit`. Use a publicly accessible website address in the POST request JSON (`{ "url": "https://example.com" }`).

This preliminary implementation requires security hardening and a full test pass before handling unrestricted public traffic.
