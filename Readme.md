### work-env
 ![example](https://raw.githubusercontent.com/JudeQuintana/work-env/master/work_env.jpg)

macOS Monterey M1

### Intro
I've invested a significant amount of time to build this work(flow)
environment especially the theme. Each tmux window is a workspace
and I'm able to navigate and manipulate my environment ( ie windows,
panes, code) from only the CLI (no mouse) with precision and speed.
Thought it would be nice to share it with the rest of the world. Yeah
I could've wrote a script but for me it's more of an excersize in
documenting and following instructions. Hope it helps your workflow!

NOTE: any `mv` commands means moving the repsective file from this git
repo.

- MacOS:
    - Map Caps Lock Key to Control
      - System Preferences -> Keyboard -> Modifier Keys
    - install flycut, multi-clipboard for the system, `shift-ctrl-v` +
      `left` or `right` arrow keys to pick which clipboard to paste
    - install lastpass, for quick password access
      - use `shift-cmd-L`, type name (navigate with arrows), `ctrl-C` (copy
        highlighted matching label)
    - install Spectacle, to allow for arranging MacOS windows via key
      shortcuts.

- Chrome Browser:
    - install Vimium (vim controls for browsing)

- Install:
    - iTerm2: download stable from https://www.iterm2.com/downloads.html
    - homebrew: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
    - zsh: `brew install zsh zsh-completions`
    - ohmyzsh `sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
      - `mv .zshrc ~`

iTerm2:
  - Install theme:
     - git clone https://github.com/dracula/iterm.git
     - Preferences -> Profile -> Colors
     - import Dracula.itermcolors
     - set Dracula color preset

Via Homebrew
  - install/upgrade:
      - `brew install tmux git hub gh vim the_silver_searcher httpie reattach-to-user-namespace ctags jq htop thefuck tfenv ccat bat ipcalc hugo`

Vim:
  - Install janus (https://github.com/carlhuda/janus)
    - `curl -L https://bit.ly/janus-bootstrap | bash`, syntax hilighting
      plugins, etc.
    - `cd $HOME/.vim/janus/vim/tools/fugitive && git checkout
      master`, fixes issues with latest vim
    - `cd $HOME/.vim/janus/vim/tools/&& git checkout master`, fixes issues with
      latest vim

    - `mkdir ~/.janus` and `git clone` these plugin repos in it:
       - `git clone https://github.com/dracula/vim` Darcula Vim Theme
         NOTE: this theme works great on `master` branch. Also an older commit also looks good, try comparing with `git checkout 0743d3d`.
       - `git clone https://github.com/vim-airline/vim-airline`
       - `git clone https://github.com/vim-airline/vim-airline-themes`
       - `git clone https://github.com/qpkorr/vim-bufkill`
       - `git clone https://github.com/fatih/vim-go`
       - `git clone https://github.com/hashivim/vim-terraform`
       - `git clone https://github.com/yssl/QFEnter.git`
       - `git clone https://github.com/godlygeek/tabular.git`
       - `git clone https://github.com/tpope/vim-bundler`
       - `git clone https://github.com/tpope/vim-rails.git`
       - `git clone https://github.com/tpope/vim-surround.git`
       - `git clone https://github.com/tpope/vim-dadbod`
       - `git clone https://github.com/szw/vim-tags`
       - `git clone https://github.com/majutsushi/tagbar`
       - `git clone https://github.com/kkvh/vim-docker-tools`
       - `git clone https://github.com/Xuyuanp/nerdtree-git-plugin` then
         `git checkout f522a09` for stable functionality, trying to
figure out how to get `master` working
    - `mv .vim.before ~`
    - `mv .vim.after ~`

OhMyZSH `git-open` Plugin:
  - `cd ~/.oh-my-zsh/custom/plugins`
  - `git clone https://github.com/paulirish/git-open.git`


rvm (https://rvm.io/)
  - install: `curl -sSL https://get.rvm.io | bash -s stable` and follow
    sourcing instructions at the end
  - install ruby 2.5.5 `rvm install 3.0.3` and `rvm --default use 3.0.3`
  - install tmuxinator: `gem install tmuxinator`

Tmux:
  - set up tmuxinator config
    - `mkdir ~/.tmuxinator` and `mv hustle.yml ~/.tmuxinator/`
    - `mkidr ~/bin` and `mv tmuxinator.zsh ~/bin/` (you'll need to add
      `~/bin` to your `PATH`)

  - clone this repo anywhere and install fonts
    - `git clone https://github.com/powerline/fonts`
    - run `./install.sh`

  - clone this repo anywhere
      - `git clone https://github.com/jimeh/tmux-themepack`
      - `mv .tmux.conf ~/.tmux.conf`
      - may need to edit `.tmux.conf` to have `source-file` point to
        `tmux-themepack/powerline/default/blue.tmuxtheme`

iTerm2:
  - Load `iterm/profile.json`
  - Or do the following:
    - under preferences -> profiles -> text
    - set fonts
      - ascii font - 13pt Monaco
      - non ascii font - 13pt source code pro for powerline
    - under preferences -> profiles -> window
      - background image from
        https://images7.alphacoders.com/321/thumb-1920-321966.jpg
    - under preferences -> profiles -> keys
      - map hot keys according to `hexcodes1.png` and `hexcodes2.png`
      - ^this is so that we dont have to press tmux leader key `ctrl-q` + tmux-cmd, we
        just map `ctrl-q` to `cmd` key, for easier/faster typing

FINAL:
  - Quit iterm
  - load iterm
  - enter the command `m` at the terminal and everything SHOULD spin up
    (first startup will be SLOW on Intel but not M1)
  - Once the tmux env is running, you can close and reopen iterm, press
    `m` and you're instantly back in your tmux session.


### Controls

## Tmux

Navigation
 - Panes:
   - Left: `cmd-h`
   - Up: `cmd-k`
   - Down: `cmd-j`
   - Right: `cmd-l`
   - Zoom In/Out: `cmd-z`
   - Create new vertical pane: `cmd-|`
   - Create new horizontal pane: `cmd--`(hyphen)
   - Move Pane Left: `cmd-{`
   - Move Pane Right: `cmd-}`
   - scroll buffer: `cmd-[`
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
   - Next Window (Right): `cmd-p`
   - Prev Window (Left): `cmd-shift-p`

 - Other:
   - any other tmux that are not mapped via hex codes use `ctrl-q` for
     tmux leader key


## Vim
 - Leader Key (lkey): `,`

 - Open/Close NerdTree file browser: `lkey-n`
   - Open file in current pane: `return`
   - Open file split vertical: `s`
   - Open file split horizontal: `i`
   - Show hidden files: `I`

 - navigate open panes
   - left `cmd-w` then `h`, Up `cmd-w` then `h`, Down `cmd-w` then `j`, Right `cmd-w` then `l`
   - if several open panes are displayed, you can zoom in/out to one
     pane: `cmd-w` then `o` (note: sometimes vim doesnt remember the
last pane configuration when zooming out, not sure why)
   - to align open panes: `cmd-w` then `=` (note usually use this when
     panes get shifted when zooming in/out of tmux pane with vim open)
   - Shift current pane to far left: `cmd-w` then `H`
   - Shift current pane to far right: `cmd-w` then `L`
   - if all panes are vertically split, then organize them horizontally
      - select each pane: `cmd-w` then `J` or `K`
   - if all panes are horizontally split, then organize them vertically
      - select each pane: `cmd-w` then `H` or `L`
 - Close Open Panes
   - Close open pane but keep open buffer: `:q`
   - Close open pane and close open buffer: `:bd`
   - Close open buffer but and replace open pane with next open buffer:
     `:BD`

 - if you want to find where the current file (open buffer) is located:
   `lkey-r`

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
       you can tab expand the file name here without typing full path
     - split horizontal open but not displayed buffer: `:sb filename`
       you can tab expand the file name here without typing full path

 - Step through open buffers using the current open buffer
  - Left `ctrl-h`, Right `ctrl-l`

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
   navigate or edit. vim mode `i` for insert (exit vim mode). if editing a long command in vim mode type `v` to edit command
line in a vim editor (qw) to save and exit.  sometimes you'll get a strange `execute:` mode (idk what it is for yet) just `ctrl-c` to exit execute mode
 - find previous commands as prefix (like ctrl-r), to scroll through
   history for commands that begin with ssh: `ssh` then use `up arrow`
to show only previous commands that begin with ssh.
 - cd into last dir: `-`
 - cd into home dir: `~`
 - cd into directory above my current dir: `..` back one dir, `...` back two dirs, `....`, etc.

 - I use the following ZSH plugins, look them up if you want to know
   more: `git rails vi-mode history-substring-search osx extract z web-search docker thefuck git-open`
 - check out all the amazing git command aliases with `alias|grep git`,
 - my favs: `gl` - git pull, `gp` - git push, `glol`- colorful logs, `gaa` - git add all, `gcmsg 'you know my steez'` - commit message, `gup` - rebase, `gco -b new-branch` - make new branch, `gcm` - checkout master

