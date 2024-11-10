# Termux Configure

**useful links**

[Termux Wiki](https://wiki.termux.com/wiki/Main_Page)

[Termux 高级终端安装使用配置教程 | 国光](https://www.sqlsec.com/2018/05/termux.html)

## storage setup

```sh
termux-setup-storage
```

this command will make termux access your device storage, so you can share files with termux.

## font change

download your font, (nerd font maybe), and 

```sh
mv path/to/your/font.ttf ~/.termux/font.ttf
```

reload settings,

```sh
termux-reload-settings
```

or just open new session.

## shell config

I use zsh, and oh-my-zsh to decorate shell.

```sh
pgk install zsh
```

```sh
chsh
```

 and enter `zsh`

exit this session and  reopen termux

you will see zsh configuration function for first use.

use oh-my-zsh

jsut follow basic installation in [ohmyzsh/ohmyzsh](https://github.com/ohmyzsh/ohmyzsh?tab=readme-ov-file)

eg 

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

change theme 

```sh
vim ./zshrc
```

and edit your theme and run `source .zshrc`

## change welcome context

```sh
vim $PREFIX/etc/motd
```

## packages

```sh
pkg install git vim wget ssh 
```

this will install necessary packages you may need, to be add...

## code-server

[Termux - code-server Docs](https://coder.com/docs/code-server/termux#install)

jsut follow the tutorial

## alias

```sh
alias codes="code-server --auth none"
alias sshub="ssh usr@yourip"
```

`sourve .zshrc`

## Using termux-backup

[Backing up Termux - Termux Wiki](https://wiki.termux.com/wiki/Backing_up_Termux)

I prefer use `~storage/downloads` path.

backup

```sh
tar -zcf storage/downloads/termux-backup.tar.gz -C /data/data/com.termux/files ./home ./usr
```

restore

```sh
tar -zxf storage/downloads/termux-backup.tar.gz -C /data/data/com.termux/files --recursive-unlink --preserve-permissions
```
