# Checkmk extension for Windows Server Role discovery

![build](https://github.com/7meis/checkmk_win_role/workflows/build/badge.svg)
![flake8](https://github.com/7meis/checkmk_win_role/workflows/Lint/badge.svg)
![pytest](https://github.com/7meis/checkmk_win_role/workflows/pytest/badge.svg)

## Description

This Extension deploys a agent plugin to windows server to discover host lables for the installed windows server roles like Active Directory, DNS etc.

## How to use
- Download the artefact from this Repo - GitHub Actions - Build Task
- Install mkp package to your site
- Configure the WATO rule named "Windows Server Role Label Discovery" and deploy the plugin to all Windows hosts (use CheckMK labels to assign the rule dynamic)
- Bake the agents and wait for discover the winrole labels

## Development

For the best development experience use [VSCode](https://code.visualstudio.com/) with the [Remote Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension. This maps your workspace into a checkmk docker container giving you access to the python environment and libraries the installed extension has.

## Directories

The following directories in this repo are getting mapped into the Checkmk site.

* `agents`, `checkman`, `checks`, `doc`, `inventory`, `notifications`, `pnp-templates`, `web` are mapped into `local/share/check_mk/`
* `agent_based` is mapped to `local/lib/check_mk/base/plugins/agent_based`
* `nagios_plugins` is mapped to `local/lib/nagios/plugins`

## Continuous integration
### Local

To build the package hit `Crtl`+`Shift`+`B` to execute the build task in VSCode.

`pytest` can be executed from the terminal or the test ui.

### Github Workflow

The provided Github Workflows run `pytest` and `flake8` in the same checkmk docker conatiner as vscode.
