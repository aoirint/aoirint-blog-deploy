# aoirint-blog-deploy

- <https://blog.aoirint.com>

Repository to deploy blog.aoirint.com.

[![Deploy](https://github.com/aoirint/aoirint-blog-deploy/actions/workflows/docker-deploy.yml/badge.svg)](https://github.com/aoirint/aoirint-blog-deploy/actions/workflows/docker-deploy.yml)


## Deploy workflow

```mermaid
flowchart TB
    subgraph legend
        branch[repo: branch]
        workflow([repo: workflow])
    end
    gatsby[aoirint/aoirint-blog-gatsby2: main]--push-->gatsby-dispatch
    gatsby-dispatch([aoirint/aoirint-blog-gatsby2: Dispatch workflow])--workflow_dispatch-->deploy([aoirint/aoirint-blog-deploy: Deploy to GitHub Pages])
    contents[aoirint/aoirint-blog-contents: main]--push-->contents-dispatch
    contents-dispatch([aoirint/aoirint-blog-contents: Dispatch workflow])--workflow_dispatch-->deploy
    this[aoirint/aoirint-blog-deploy: main]--push-->deploy
```

- Deploy: <https://github.com/aoirint/aoirint-blog-deploy>
- Gatsby: <https://github.com/aoirint/aoirint-blog-gatsby2>
- Contents: <https://github.com/aoirint/aoirint-blog-contents>
