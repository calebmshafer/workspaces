# iTwin.js Workspace

> Note this is the main workspace used to develop and diagnose issues with iTwin.js.

This workspace is setup to support both the iTwin.js core repository and all of its dependent repos and folders.

The following repos are opened within this workspace:

- [imodeljs](https://github.com/imodeljs/imodeljs)
- [auth-clients](https://github.com/itwin/auth-clients)
- [imodel-clients](https://github.com/itwin/imodel-clients)
- [workspaces](https://github.com/itwin/imodel-clients) (this repo)

The connecting of the multiple repositories is handled by using Rush to connect both repos.

The launch configurations are setup to support debugging via any app web app within the repos. However, if you'd like to debug the test-apps in the iModel.js repo you'll need to do that directly or add the config.

## Required Setup

In order for the repo connecting to work, there are a few manual steps required.

1. Update the `itwinjs.code-workspace` folder to the correct names of each repo.
    - It currently assumes the iModel.js repo is called "imodeljs" as a peer of this repo. Similar assumptions are made for each of the other repos.
2. Update the [rush.json](./rush.json) with the same paths as updated above. Each project required is relatively linked to the other repo, so the path updates are required.

> WARNING: The above steps will break both repos being connected from working in a non-workspace setting.
> The way to fix it is by running a `rush purge` and `rush install` directly with the repo you'd like to get back into a current working state.
