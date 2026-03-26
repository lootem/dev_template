# Lootem's Dev Template

* Develop in containers with [VSCode dev containers](https://code.visualstudio.com/docs/devcontainers/containers)
* Install and configure formatting extensions such as `black` and `prettier-vscode`
* Define code editor settings with `.vscode/settings.json` and `.editorconfig`

## Get started

1. `git clone https://github.com/lootem/dev_template.git`
2. Remove unnecessary lang folders, ex. `.devcontainer/python/`
3. Move files to their relevant directory
    * `.devcontainer/<lang>/devcontainer.json` > `.devcontainer/devcontainer.json`
    * `.devcontainer/<lang>/Dockerfile` > `.devcontainer/Dockerfile`
    * `.devcontainer/<lang>/launch.json` > `.vscode/launch.json`
4. Customize as required