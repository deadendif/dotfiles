# Dotfiles
The repository is used to store dotfiles to unify my work environment of
different Linux machine, which includes configure file of bash, zsh, vim,
screen. 


## Dotfiles List

Dotfiles about: bash, zsh, [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh),
vim, screen. As to vim, I use [pathogen.vim](https://github.com/tpope/vim-pathogen) 
to manage 'runtimepath'.

## Installation

##### 1. Download

```shell
git clone https://github.com/deadEnding/dotfiles.git ~/dotfiles
git submodule update --init --recursive
```

##### 2. Deployment 

```shell
cd ~/dotfiles && ./makesymlinks.sh
```

## Customize
You can also add other dotfiles, and the dotfile can be plain file or another
repository. One thing to be noted is that the dotfiles or their superior directory 
must be appended to the variable `file` in shell script `makesymlinks.sh`, so it will
create symlink when executing `makesymlinks.sh`.

#### Add Plain File/Folder

##### 1. Copy plain file/folder to the repository
```shell
cp .<dotfile-name> ~/dotfiles/<dotfile-name>
```
*Warning*: Pay attention to the name change of dotfile. Don't forget to remove the dot 
when copying the dotfile.

##### 2. Optionally, modify makesymlinks.sh
Edit file `makesymlinks.sh`, append `<dotfile-name>` to the variable `files`.

#### Add Another Repository
It's a little troublesome to add another repository.

##### 1. add repository as a submodule
```shell
git submodule add <url> <local-path>
```

##### 2. Optionally, modify makesymlinks.sh
Edit file `makesymlinks.sh`, append top directory to the variable `files`.
