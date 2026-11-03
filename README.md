# Square Badge Maker

Single-page app that places photos on square or round pin-back badge templates and lays them out on an A4 sheet.
Saves A4 PDF, A4 PNG and single-badge PNG files in the browser. No backend, no build step.

## Deploy with Coolify

1. Push this folder to a Git repository (GitHub, GitLab, Gitea or any Git server Coolify can reach).
2. In Coolify: **Project > New Resource > Public Repository** (or Private Repository with a deploy key / GitHub App).
3. Choose the repository and branch.
4. Set **Build Pack** to **Dockerfile**. Set **Ports Exposes** to `80`.
5. Under **Domains**, enter the address you want, for example `https://badges.example.com`.
   Point that name's DNS A record at the Coolify server first. Coolify issues the HTTPS certificate itself.
6. Click **Deploy**. Turn on **Auto Deploy** if you want every push to redeploy.

The container serves `index.html` with nginx and answers `/healthz` for the health check.

## Run locally

    docker build -t badge-maker .
    docker run --rm -p 8080:80 badge-maker

Then open http://localhost:8080
