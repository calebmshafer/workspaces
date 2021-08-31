# iTwin Viewer and iModel.js Workspace

This workspace is setup to support both the iModel.js core repository and the iTwin Viewer repo.

The connecting of the two repositories is handled by using Rush to connect both repos

The launch configurations are setup to support debugging via any app within the Viewer repo into the imodeljs repo. However, if you'd like to debug the test-apps in the iModel.js repo you'll need to do that directly or add the config.

## Required Setup

In order for the repo connecting to work, there are a few manual steps required.

1. Update the `viewer-itwinjs.code-workspace` folder to the correct names of each repo.
    - It currently assumes the iModel.js repo is called "imodeljs2" as a peer of this repo and the Viewer repo is "viewer" also as a peer.
2. Update the [rush.json](./rush.json) with the same paths as updated above. Each project required is relatively linked to the other repo, so the path updates are required.
3. Update all of the references to the packages/projects defined in the `rush.json` to be referenced as part of the workspace, "workspace:*".
  a) Do this by, searching for `@itwin/desktop-viewer-react": ".*"` and replacing with `@itwin/desktop-viewer-react": "workspace:*"`

> WARNING: The above steps will break both repos being connected from working in a non-workspace setting.
> The way to fix it is by running a `rush purge` and `rush install` directly with the repo you'd like to get back into a current working state.
