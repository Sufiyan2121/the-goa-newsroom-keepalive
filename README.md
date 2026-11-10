# The Goa Newsroom — Keepalive Monitor

Dedicated **public** GitHub Actions keepalive repository for **The Goa Newsroom** (`the-goa-newsroom-daemon` on Render Free Tier).

Keeping this workflow in an isolated public repository ensures unlimited free GitHub Actions minutes (~5,040 runs/month at ~8-minute cadence) while the main backend (`Sufiyan2121/the-goa-newsroom`) and web portal (`Sufiyan2121/the-goa-newsroom-web`) remain **Private**.

## Workflow
- [`.github/workflows/render-keepalive.yml`](.github/workflows/render-keepalive.yml)
  - Schedule: `4,12,20,28,36,44,52 * * * *` (off-minute 8-minute cadence under Render's 15-minute idle timeout)
  - Target: `https://the-goa-newsroom-daemon.onrender.com/healthz`
  - Manual trigger: `workflow_dispatch`

> **Note:** GitHub Actions automatically pauses scheduled workflows in repositories with no repository activity for 60 consecutive days; occasionally re-enable via **Actions -> Render Daemon Keepalive** if needed.
