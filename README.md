These are the dot config files I use in my accounts.

They are managed through [homeshick](https://github.com/andsens/homeshick).

In order to deploy them, just use `homeshick clone jasuarez/dotfiles` and it will clone and symlinks created for the config files.

If any of the file already exists in your home, it will skip them.


# Installing homeshick

Homeshick is based on [homesick](https://github.com/technicalpickles/homesick), but entirely using bash instead of Ruby. So it is very easy to install.

```
git clone https://github.com/andsens/homeshick.git $HOME/.homesick/repos/homeshick

cat <<EOF >> ~/.bashrc
# Enable homeshick
if [ -d ~/.homesick/repos/homeshick ]; then
    source ~/.homesick/repos/homeshick/homeshick.sh
    source ~/.homesick/repos/homeshick/completions/homeshick-completion.bash
fi
EOF
```

# Using homeshick

To deploy this config files in your machine, just run

```
homeshick clone jasuarez/dotfiles
```

It will ask if you want to create the symlinks. If any file or directory already exists (like for example your own `.emacs.d`) it won't overwrite it.

To check if there are new versions of `homeshick` or ` dotfiles` use

```
homeshick check
```

To pull new changes use

```
homeshick pull
```

and to deploy new configuration files

```
homeshick link
```
