# Docker Vim Go

A Docker container to run neovim with plugins to assist Go development.

## Requirements

- [Docker][docker]

## Installation

1. Clone this repository:

    ```shell
    git clone git@github.com:thled/docker-vim-go.git
    ```

1. Change to project directory:

    ```shell
    cd docker-vim-go
    ```

1. Build image (`arg` for Copilot is optional):

    ```shell
    docker build --build-arg COPILOT_TOKEN=XXX -t gvim .
    ```

## Usage

```shell
docker run --rm -it -v (pwd):/data gvim
```

## Misc

- Useful key bindings: <https://gist.github.com/thled/a6fcf4a02108598ae9ba5a8ab01d84e0#editor-neovim>
- Remap detach keys:

    ```shell
    echo '{ "detachKeys": "ctrl-q,q" }' > ~/.docker/config.json
    ```

- Save as alias "gvim":
  - Fish:

  ```shell
  function gvim
    docker run --rm -it -v (pwd):/data gvim
  end
  funcsave gvim
  ```

  - Bash:

  ```shell
  echo 'alias gvim="docker run --rm -it -v $(pwd):/data gvim"' >> ~/.bashrc
  ```

[docker]: https://docs.docker.com/install

