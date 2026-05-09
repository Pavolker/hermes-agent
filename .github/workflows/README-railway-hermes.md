# Railway emergency controls for Hermes

These workflows provide manual GitHub Actions buttons to restart or redeploy the Railway service `hermes` in the `production` environment.

## Required secret

Add this repository secret before using the workflows:

- `RAILWAY_TOKEN`: Railway Project Token scoped to the `HERMES` project / `production` environment.

Railway documents Project Tokens for CI/CD here:
- https://docs.railway.com/cli/deploying

## Workflows

- `Railway Restart Hermes`
  - Uses `railway restart`
  - Reuses the current deployment image without rebuilding
  - Best for a stuck process or transient crash
  - Docs: https://docs.railway.com/cli/restart

- `Railway Redeploy Hermes`
  - Uses `railway redeploy`
  - Creates a fresh deployment from the latest deployed source
  - Best when restart is not enough
  - Docs: https://docs.railway.com/cli/redeploy

## Mobile use

1. Open the GitHub mobile app.
2. Go to the repository.
3. Open `Actions`.
4. Choose `Railway Restart Hermes` or `Railway Redeploy Hermes`.
5. Tap `Run workflow`.

GitHub manual workflows are based on `workflow_dispatch`:
- https://docs.github.com/en/actions/using-workflows/triggering-a-workflow
