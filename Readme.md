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
      - `brew install git vim tmux the_silver_searcher httpie reattach-to-user-namespace ctags git jq htop thefuck terraform ccat hub`

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
       - vim-docker-tools (https://github.com/kkvh/vim-docker-tools)
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

## Tmux

Navigation
 - Panes:
   - Left: `cmd+h`
   - Up: `cmd+k`
   - Down: `cmd+j`
   - Right: `cmd+l`
   - Zoom In/Out: `cmd+z`
   - Create new vertical pane: `cmd+|`
   - Create new horizontal pane: `cmd+-`(hyphen)
   - Move Pane Left: `cmd+{`
   - Move Pane Right: `cmd+}`
   - scroll buffer: `cmd+[`
     - search up: `?`
     - search down: `/`
     - use vim controls to navigate left(`h`), Up(`k`), Down(`j`),
       Right(`l`), back page(`ctrl-b`), forward page(`ctrl-f`), etc
     - to copy text, enter highlight mode `v` (start highlight at
       current cursor) or `V` (start highlight entire line), use vim
controls to select desired text. `esc` to stop highlight mode but stay
in scroll mode. `return` to copy selected text to system clipboard, will
exit scroll mode.
     - clear scroll buffer: `ctrl-k`

 - Windows:
   - Next Window (Right): `cmd+p`
   - Prev Window (Left): `cmd+P`

 - Other:
   - any other tmux that are not mapped via hex codes use `ctrl+q` for
     tmux leader key


## Vim
 - Leader Key (lkey): `,`

 - Open/Close NerdTree file browser: `lkey+n`
   - Open file in current pane: `return`
   - Open file split vertical: `s`
   - Open file split horizontal: `i`
   - Show hidden files: `I`

 - navigate open panes
   - left `cmd+w` then `h`, Up `cmd+w` then `h`, Down `cmd+w` then `j`, Right `cmd+w` then `l`
   - if several open panes are displayed, you can zoom in/out to one
     pane: `cmd+w` then `o` (note: sometimes vim doesnt remember the
last pane configuration when zooming out, not sure why)
   - to align open panes: `cmd+w` then `=` (note usually use this when
     panes get shifted when zooming in/out of tmux pane with vim open)
   - Shift current pane to far left: `cmd+w` then `H`
   - Shift current pane to far right: `cmd+w` then `L`
   - if all panes are vertically split, then organize them horizontally
      - select each pane: `cmd+w` then `J` or `K`
   - if all panes are horizontally split, then organize them vertically
      - select each pane: `cmd+w` then `H` or `L`
 - Close Open Panes
   - Close open pane but keep open buffer: `:q`
   - Close open pane and close open buffer: `:bd`
   - Close open buffer but and replace open pane with next open buffer:
     `:BD`

 - if you want to find where the current file (open buffer) is located:
   `lkey+r`

 - Search file system by file name: `ctrl-p` then start typing name of file, will
   list files that match, use `esc` to exit search mode.
   - Select files, up and down: `up/down arrow keys`
     - Open file in current pane: `return`
     - Open file in vertical pane: `ctrl-v`
     - Open file in horizontal pane: `ctrl-x`

 - Search open buffers by file name: `ctrl-p` then `ctrl-f` then start typing name of file, will
   list files that match, use `esc` to exit search mode.
   - Select files, up and down: `up/down arrow keys`
     - Open file in current pane: `return`
     - Open file in vertical pane: `ctrl-v`
     - Open file in horizontal pane: `ctrl-x`
   - Since you can see a list of open buffers at the top even though
     they may not be displayed you can open them in splits by name
     - split vertical open but not displayed buffer: `:vert sb filename`
       you can tab expand the file name here without type full path
     - split horizontal open but not displayed buffer: `:sb filename`
       you can tab expand the file name here without type full path

 - Step through open buffers using the current open buffer
  - Left `ctrl+h`, Right `ctrl+l`

 - Grep for text in all files: `\\`(single backslash) then type text
   you want to search for, then `return`. Will open QuickFix List pane.
     - use vim controls to navigate left(`h`), Up(`k`), Down(`j`),
       Right(`l`)
       - Open file in current pane: `return`
       - Open file in vertical pane: `ctrl-v`
       - Open file in horizontal pane: `ctrl-x`
     - close QuickFix list pane: `:ccl`

 - to see history of edits on a file: `F5`, step through history, `:q`
   to close

 - Git blame: `:Gblame`, `:q` to close

 - Rename file in open buffer: `:Rename new-file-name`

## Terminal
 - quickly cd into previous directories w/o typing absolute path: `z dir-name`
 - enter vim mode on command line: `esc` then use vim controls to
   navigate or edit. if editing a long command type `v` to edit command
line in a vim editor. `ctrl-c` to exit vim mode
 - find previous commands as prefix (like ctrl-r), to scroll through
   history for commands that begin with ssh: `ssh` then use `up arrow`
to show only previous commands that begin with ssh.
 - cd into last dir: `-`
 - cd into directory above my current dir: `..` back one dir, `...` back two dirs, `....`, etc.

 - I use the following ZSH plugins, look them up if you want to know
   more: git rails vi-mode history-substring-search osx extract z web-search docker thefuck git-open

