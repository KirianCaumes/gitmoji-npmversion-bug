# testmoji

⚠️ Temporary project, to be deleted ⚠️

## Run

Open folder with Visual Studio Code.

Install `ms-vscode-remote.remote-containers` extension.

Open Visual Code in Container: click on the green button at the bottom left of the screen, and choose `Open in Container` (Docker required).

Wait for container to setup, and that's it!

Test issue with:

```sh
npm run tag --to=1.0.4
# OR
npm version --commit-hooks=false --force -m "🔖 %s" "1.0.4"
```
