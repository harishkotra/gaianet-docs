---
sidebar_position: 9
---

# Uninstalling the Gaia CLI

To uninstall or clear the environment, run the following command.

```
curl -sSfL 'https://github.com/GaiaNet-AI/gaianet-node/releases/latest/download/uninstall.sh' | bash
```

**Important reminder: This command will remove all the GaiaNet-related files, including the `nodeid.json`. It's your responsibility to keep your nodeid.json safe. If you want to run the same node after reinstalling, please save the `nodeid.json` file and `frpc.toml` file carefully.**

//Add a note about upgrade instead of uninstall