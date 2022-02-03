---
title: "Use git aliases"
date: 2022-02-03
draft: true
---


We all work with some kind of version control systems, and if you work with git as I do, you should know how it works and what it can do for you really well. 

One of the features which can improve our development workflow are git aliases. And here I'm presenting to you a very good git config with nice aliases (and other git configurations) which will speed up your typing when using git. Also you don't need to invent them by yourself, just look at the config file and you will immiedietaly recoginze your frequently used commands and how you can use them faster by typing only few letters.

So here is the aformentioned [git config](https://github.com/jakubnabrdalik/gitkurwa/blob/master/config) (All credits goes to [Jakub Nabrdalik](https://github.com/jakubnabrdalik) for sharing this config with a community, this config saved me a lot of time :smile: thank you! :bow:)
and you can install it with this command
```bash
echo "" >> ~/.gitconfig && curl https://raw.githubusercontent.com/jakubnabrdalik/gitkurwa/master/config >> ~/.gitconfig
```

Be aware that this script appends git configuration to your existing git configuration so you can end up with some duplicated configuration. If you're unsure if it's safe for you then just copy interesting aliases from [git config](https://raw.githubusercontent.com/jakubnabrdalik/gitkurwa/master/config) to your ```~/.gitconfig``` file