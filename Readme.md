### work-env
 ![example](https://raw.githubusercontent.com/JudeQuintana/work-env/master/work_env.jpg)

MacOS High Sierra

NOTE: any `mv` commands means moving the repsective file from this git
repo.

- MacOS:
    - Map Caps Lock Key to Control
    - System Preferences -> Keyboard -> Modifier Keys

- Install:
    - iTerm2: download stable from https://www.iterm2.com/downloads.html
    - homebrew: `ruby -e "$(curl -fsSL https://raw.zshhubusercontent.com/Homebrew/install/master/install)"`
    - zsh: `brew install zsh zsh-completions`
    - ohmyzsh `sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
      - `mv .zshrc ~`

iTerm2:
  - Install theme:
     - git clone (https://github.com/dracula/iterm.git)
     - import Dracula.itermcolors

Via Homebrew
  - install/upgrade:
      - `brew install vim tmux the_silver_searcher reattach-to-user-namespace ctags git jq htop thefuck terraform`
      - Optional: `brew install source-highlight`, this is a big install. I use this for syntax highlighting
        in less. If you dont want this comment out the following lines out of `.zshrc`
      - ```
          LESSPIPE=`which src-hilite-lesspipe.sh`
          export LESSOPEN="| ${LESSPIPE} %s"
          export LESS='-R'
        ```

Vim:
  - Install janus (https://github.com/carlhuda/janus)
    - `curl -L https://bit.ly/janus-bootstrap | bash`

    - `mkdir ~/.janus` and `git clone` these plugin repos in it:
       - dracula-theme (https://github.com/dracula/vim)
         NOTE: currently, master breaks some syntax highlighting
plugins so `git checkout 0743d3d` is necessary, after initial cloning.
       - vim-airline (https://github.com/vim-airline/vim-airline)
       - vim-airline-themes (https://github.com/vim-airline/vim-airline-themes)
       - vim-bufkill (https://github.com/qpkorr/vim-bufkill)
       - vim-go (https://github.com/fatih/vim-go)
       - vim-terraform (https://github.com/hashivim/vim-terraform)
       - qfenter (https://github.com/yssl/QFEnter.git)
       - tabular (https://github.com/godlygeek/tabular.git)
       - vim-bundler (https://github.com/tpope/vim-bundler)
       - vim-rails (https://github.com:tpope/vim-rails.git)
       - vim-surround (https://github.com:tpope/vim-surround.git)
       - vim-db (https://github.com/tpope/vim-dadbod)
       - vim-tags (https://github.com/szw/vim-tags)
       - tagbar (https://github.com/majutsushi/tagbar)
       - vim-zoom (https://github.com/dhruvasagar/vim-zoom)
      - `mv .vim.before ~`
      - `mv .vim.after ~`

OhMyZSH `git-open` Plugin:
  - `cd ~/.oh-my-zsh/custom/plugins`
  - `git clone git@github.com:paulirish/git-open.git`


rvm (https://rvm.io/)
  - install: `curl -sSL https://get.rvm.io | bash -s stable` and follow
    sourcing instructions at the end
  - install tmuxinator: `gem install tmuxinator`

Tmux:
  - set up tmuxinator config
    - `mkdir ~/.tmuxinator` and `mv hustle.yml ~/.tmuxinator/`
    - `mkidr ~/.bin` and `mv tmuxinator.zsh ~/.bin/`

  - clone this repo anywhere and install fonts
    - `git clone https://github.com/powerline/fonts`
    - run `./install.sh`

  - clone this repo anywhere
      - `git clone tmux-themepack (https://github.com/jimeh/tmux-themepack)`
      - `mv .tmux.conf ~/.tmux.conf`
      - may need to edit `.tmux.conf` to have `source-file` point to
        `tmux-themepack/powerline/default/blue.tmuxtheme`

iTerm2:
  - under preferences -> profiles -> text
  - set fonts
    - ascii font - 13pt Monaco
    - non ascii font - 13pt source code pro for powerline
  - under preferences -> profiles -> window
    - background image from
      https://images7.alphacoders.com/321/thumb-1920-321966.jpg
 - under preferences -> profiles -> keys
   - map hot keys according to `hexcodes1.png` and `hexcodes2.png`
   - or load `iterm/profiles.json`

FINAL:
  - Quit iterm
  - load iterm
  - enter the command `m` at the terminal and everything SHOULD spin up


### Controls

TODO


