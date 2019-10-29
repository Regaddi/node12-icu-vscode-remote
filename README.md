# Reproduction for incompatibility of VSCode Remote and node12 images with built-int ICU

## Steps to reproduce

1. Clone repository and open with latest (1.39.2, 6ab598523be7a800d7f3eb4d92d7ab9a66069390) VSCode
2. Install [Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) extension
3. Open folder in container
4. Choose "From 'Dockerfile'"
5. Connection fails with error in Terminal

```
Run: docker exec -w /root/.vscode-server/bin/6ab598523be7a800d7f3eb4d92d7ab9a66069390 -e SHELL=/bin/ash -e VSCODE_AGENT_FOLDER=/root/.vscode-server c275093638cfe9aabb75981922ecca19e158cc848dc6dde231df13597f49b03d /root/.vscode-server/bin/6ab598523be7a800d7f3eb4d92d7ab9a66069390/server.sh --disable-user-env-probe --port 0
/root/.vscode-server/bin/6ab598523be7a800d7f3eb4d92d7ab9a66069390/node: could not initialize ICU (check NODE_ICU_DATA or --icu-data-dir parameters)
Command failed: docker exec -w /root/.vscode-server/bin/6ab598523be7a800d7f3eb4d92d7ab9a66069390 -e SHELL=/bin/ash -e VSCODE_AGENT_FOLDER=/root/.vscode-server c275093638cfe9aabb75981922ecca19e158cc848dc6dde231df13597f49b03d /root/.vscode-server/bin/6ab598523be7a800d7f3eb4d92d7ab9a66069390/server.sh --disable-user-env-probe --port 0
```
