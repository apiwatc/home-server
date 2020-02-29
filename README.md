# **Ubuntu Server**

**Table of Contents**
1. [Web Server](https://github.com/apiwatc/home-server/tree/master/web-server)
    - [Apache]()
    - [Nginx]()
2. [Wireless Connection](https://github.com/apiwatc/home-server/tree/master/wireless-connection)
3. [Change to zsh](#change-to-z-shell-zsh-and-install-oh-my-zsh)




#### Change to z-shell (zsh) and install Oh-My-Zsh

- Update the packages

        $ sudo apt-get update
        $ sudo apt upgrade

- Install zsh

        $ sudo apt install zsh

- Clone the Oh My Zsh repo to home

        $ git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh

- Create a New ZSH configuration file

        $ cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc

- Change your Default Shell

        $ chsh -s /bin/zsh

- Add the ZSH Syntax Highlighting

        $ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/

- Add plugins to .zshrc

        $ nano .zshrc

- Look for 'plugins=()', add plugins as you like (but too many might slow your shell down)

        plugins=(git colored-man-pages zsh-syntax-highlighting)

- Customize zsh prompt to show hostname with colors

        Go to your theme location: For example -> .oh-my-zsh/themes/robbyrussell.zsh-theme and modify them as you like

        PROMPT="%(?:%{$fg_bold[green]%}➜ $FG[011]%n%f$FG[015]@%f$FG[014]%m%f :%{$fg_bol$
        PROMPT+='%{$reset_color%}[%c]%{$reset_color%} $(git_prompt_info)'
    [Colors and formatting](https://misc.flogisoft.com/bash/tip_colors_and_formatting) and [Prompt Expansion](http://zsh.sourceforge.net/Doc/Release/Prompt-Expansion.html)

        
- Additional instructions >> [Installing ZSH](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH)
- Adding your theme >> [Themes](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)
- Customizing >> [Customization](https://github.com/ohmyzsh/ohmyzsh/wiki/Customization)
