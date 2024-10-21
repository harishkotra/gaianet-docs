---
sidebar_position: 8
---

# Install or Update the CLI

The Gaia node utilizes version control from [its source GitHub repo](https://github.com/GaiaNet-AI/gaianet-node). You can check out the GaiaNet node versions from [the releases page](https://github.com/GaiaNet-AI/gaianet-node/releases).

### Install the latest version of the Gaia node

To install the most recent version of Gaia node, run the following command line.

```
curl -sSfL 'https://github.com/GaiaNet-AI/gaianet-node/releases/latest/download/install.sh' | bash
```

The GaiaNet node will be installed in your `$HOME/gaianet` folder by default. 

> If you want to install gaianet in a different directory, you can use `curl -sSfL 'https://github.com/GaiaNet-AI/gaianet-node/releases/latest/download/install.sh' | bash -s --  --base <Full_Path> ` to specify where you want to install GaiaNet. Once you use `--base` to define a different directory, you should always add `--base <Full_Path>` to init and start your node.
> Here is an example:
> ```
> # Assume that you're in the root directory
> mkdir test
> curl -sSfL 'https://github.com/GaiaNet-AI/gaianet-node/releases/latest/download/install.sh' | bash -s --  --base $HOME/test
> gaianet init --base $HOME/test
> gaianet start --base $HOME/test
> gaianet stop --base $HOME/test
> ```

### Install the specific version of GaiaNet Node

If you want to install a particular GaiaNet node version, change the version number in the following command line.

```
curl -sSfL 'https://github.com/GaiaNet-AI/gaianet-node/releases/download/0.1.3/install.sh' | bash
```

Check out the release log [here](https://github.com/GaiaNet-AI/gaianet-node/releases).

## What's installed

If you install the GaiaNet node in the `$HOME/gaianet` directory by default, you will have the following directories and files after installation:

* The `$HOME/gaianet/bin` directory contains the GaiaNet CLI tool, frpc binary and Qdrant Vector database binary.
* The `$HOME/gaianet/` directory contains the `llamaedge-api-server.wasm` and `rag-api-server.wasm` for the LLM inference, dashboard (chatbot ui), nodeid.json for the registering your node, and gaianet-domain binary.
* The `$HOME/.wasmedge/bin` directory contains the WasmEdge Runtime CLI executable files, which serve as the LLM runtime.

## CLI options for the installer

You can use the following command line to check out all the available CLI options

```
curl -sSfL 'https://github.com/GaiaNet-AI/gaianet-node/releases/latest/download/install.sh' | bash -s -- --help
```

The output should be as follows. You can use the following options to customize your installation.

```
Usage:
  ./install.sh [Options]

Options:
  --config <Url>     Specify a url to the config file
  --base <Path>      Specify a path to the gaianet base directory
  --reinstall        Install and download all required deps
  --tmpdir <Path>    Specify a path to the temporary directory [default: /tmp]
  --ggmlcuda [11/12] Install a specific CUDA enabled GGML plugin version [Possible values: 11, 12].
  --enable-vector:   Install vector log aggregator
  --version          Print version
  --help             Print usage
```

# Update the current Gaia node

Simply run the following command to upgrade your node.

```
curl -sSfL 'https://github.com/GaiaNet-AI/gaianet-node/releases/latest/download/install.sh' | bash -s -- --upgrade
```

The `upgrade` option will keep your node id.