# Dotfiles

This repository contains all of the setup scripts that I can use to configure a new computer or workspace. The programs that
are being setup include the following.

- Neovim 0.7.0 (Including Lua API)
- Python and PyEnv
- Nodejs and NVM
- Lua and Luarocks
- Rust, Cargo, and Rustup
- Bash (rc and profile)
- Alacritty
- Exa
- scala and sbt
- Vale Setup

It will also contains scripts that will be used to differentiate between linux
and MacOS systems

## Testing procedure

1. First build the docker file

```bash
sudo docker build -t {insert name} .
```

2. Open up an interactive terminal in docker in order to make sure everything is
there


Command forked from [ls12styler/ide](https://github.com/ls12styler/ide)
```bash
function ide() {
  PROJECT_DIR=${PWD##*/}
  PROJECT_NAME=${PWD#"${PWD%/*/*}/"}
  CONTAINER_NAME=${PROJECT_NAME//\//_}
  TMUX_RESURRECT=${HOME}/.ide/${PROJECT_NAME}/tmux/resurrect
  mkdir -p ${TMUX_RESURRECT}
  ZSH=${HOME}/.ide/${PROJECT_NAME}/zsh/
  mkdir -p ${ZSH}
  touch ${ZSH}/zsh_history
  docker run --rm -it \
  -w /${PROJECT_DIR} \
  -v $PWD:/${PROJECT_DIR} \

  -v /var/run/docker.sock:/var/run/docker.sock \
  -v ~/.ssh:/home/me/.ssh \
  -v ${TMUX_RESURRECT}:/home/me/.tmux/resurrect \
  -v ${ZSH_HISTORY}:/home/me/.zsh_history \
  -e IVY_PATH=${HOME}/.ivy2 \
  -e HOST_PATH=$PWD \
  -e HOST_USER_ID=$(id -u $USER) \
  -e HOST_GROUP_ID=$(id -g $USER) \
  -e PROJECT_NAME=$PROJECT_NAME \
  -e GIT_USER_NAME="Me McMe" \
  -e GIT_USER_EMAIL="me@me.com" \
  -e KUBE_HOME="/path/to/.kube" \
  -e HELM_HOME="/path/to/.helm" \
  --name $CONTAINER_NAME \
  --net host \
  marshmalon/ide:latest
}
```
