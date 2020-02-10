# Dotfiles

This repository contains all of the seutp scripts that I can use to configure a new computer or workspace. The programs that
are being setup include the following.

- ~Neovim~
- Python and ~PyEnv~
- Nodejs and ~NVM~
- ~Lua and Luarocks~
- ~Rust, Cargo, and Rustup~
- ~Bash (rc and profile)~
- Alacritty
- Exa
- ~scala and sbt~

It will also contains scripts that will be used to differentiate between linux
and MacOS systems

## To do

- [x] Consolidate all setup files here
- [x] Create bash installation scripts
- [ ] CRON job to periodically update this repo based on updates to my own profile or init.vim
- [ ] sub repo for neovim
    - [ ] Need to at least update to match current situation
- [ ] Test this in a docker file to make sure it works for linux 
- [ ] Add a verification script      
      
## Testing procedure

1. First build the docker file

```bash
sudo docker build -t {insert name} .
```

2. Open up an interactive terminal in docker in order to make sure everything is there

