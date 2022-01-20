# rsync-deploy-action

Action to deploy site to remote server via rsync

```yml
name: Release

on:
  release:
    types:
      - released
  workflow_dispatch:

jobs:
  build:
    name: Build
    runs-on: ubuntu-latest
    steps:
      - name: Deploy files
        uses: sitkoru/rsync-deploy-action@v1
        with:
          key: ${{secrets.SSH_PRIVATE_KEY}}
          host: ${{ secrets.DEPLOY_HOST }}
          user: ${{ secrets.DEPLOY_USER }}
          target: ${{ secrets.HOST_PATH }}
```
