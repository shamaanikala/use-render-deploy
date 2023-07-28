# Use Render Deploy Action

A simple composite GitHub Action to use Render.com Deploy Hook.

**The Action is under development.**

## Usage within GitHub Actions workflow

Follow the Render.com introductions to get your Web Service Deploy Hook:
[https://render.com/docs/deploy-hooks](https://render.com/docs/deploy-hooks)

The format of a Render.com deploy webhook url is:

`https://api.render.com/deploy/srv-<RENDER_SERVICE_ID>?key=<RENDER_API_KEY>`

1. Setup secrets within the GitHub repository:

- `RENDER_SERVICE_ID`
- `RENDER_API_KEY`

2. Use this composite action within GitHub Actions workflow:

```yml
name: Example of use-render-deploy usage

on:
  push:
    - main

jobs:
  trigger_render_deploy_hook
    name: Trigger Render.com Deploy Hook
    runs-on: ubuntu-latest
    steps:
      - uses: shamaanikala/use-render-deploy@v1-alpha
        with:
          render-service-id: ${{ secrets.RENDER_SERVICE_ID }}
          render-api-key: ${{ secrets.RENDER_API_KEY }}
```
