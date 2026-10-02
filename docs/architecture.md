# Architecture

How the local Red Hat Developer Hub connects to everything it shows.

```mermaid
flowchart LR
    U[Browser] --> R[RHDH local<br/>Docker :7007]
    R --> K[Kubernetes plugin<br/>+ Topology]
    R --> G[GitHub plugins<br/>Insights, Actions, Issues, PRs]
    R --> T[TechDocs]
    R --> P[Proxy /api/proxy/wrike]
    R --> D[GitHub discovery]
    K --> S[(OpenShift Sandbox<br/>danigrilo-dev)]
    G --> H[(GitHub<br/>test-react-app)]
    T --> H
    D --> H
    P --> W[(Wrike API)]
```

## Editing the diagram

Edit the `mermaid` block above and push. TechDocs re-renders it on the next build.

TechDocs strips JavaScript from pages, so Mermaid can't render in the browser here. Instead the `kroki` MkDocs plugin sends the block to kroki.io while the docs are built and embeds the resulting SVG.
