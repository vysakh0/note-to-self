#Tactics

You should be already using Vim, and Tmux.

## Discipline
To learn a skill, all it takes is discipline and self control. When I first started learning Vim, I deliberately avoided
- using arrow keys
- mouse

It sucked but eventually paid off. These are set of tactics that one should adhere strictly to get incredible dexterity. All these will constantly evolve with new plugins or tools (like tmux), so writing this here instead of a blog post.


## Vim

### When not to come out of the text editor

#### When using Git,

- Use [vim-fugutive](https://github.com/tpope/vim-fugitive)
- Have mappings for all your git commands in your vimrc.
- **Strictly abstain from typing git commands outside your text editor.**

#### When you want to run or compile a file,

- If you want to run your python/ruby program.
- If you want to run your test file that are you are currently editing.
- If you want to npm install or bower install or gem install while you are editing.

Use [vim-dispatch](https://github.com/tpope/vim-dispatch) and have mappings for your common tasks in your vimrc!

#### When you want to grep or find a file

- If you want to find a specifc word among the files in your directory.
- If you want to quickly find a specific file.

I use [unite.vim](https://github.com/Shougo/unite.vim) and have approrpriate mappings for both these cases.
Or you could use ctrl-p plugin and other plugins for greping.

### Quick find

#### When you want to find a file in Rails project

Don't use unite.vim or ctrl-p in your Rails project or similar project where you have specialized plugin! Use **vim-rails** and once you have mappings for the common commands, file switching would be blazing fast

#### When you want to go to a method or class in your program

I use **unite-outline**, you could use plugins like **tagbar**. So avoid, scrolling through with ctrl+d or ctrl+u.

#### When you want to go to a specific word or specific line

Use **easy-motion** or **vim-sneak** to move to lines or words.

#### When you are searching or substituting for a word

- Use `set hlsearch | set incsearch` in your *vimrc*
- Check [vim-over plugin](https://github.com/osyo-manga/vim-over) that gives nice preview and word completion.
- Substituion on steriods, do use [vim-abolish](https://github.com/tpope/vim-abolish), also the coercion part of it is quite handy
- Also check ['terryma/vim-multiple-cursors'](https://github.com/terryma/vim-multiple-cursors), it makes substituion sweet!

### Autocomplete
- I use neocomplete, there are projects like youcompleteme.
- Use a snippet plugin, i use neosnippets. Also do add your own snippets.

### Text manipulation
##### must-have
- Vim-surround
- Vim-commentary or nerdcommenter
- [Vim-autopairs](https://github.com/jiangmiao/auto-pairs) is a must have plugin.
- [splitjoin.vim](https://github.com/AndrewRadev/splitjoin.vim)

**Text-objects**:
- Depending on your workflow, you could [choose a suitable vim-text-obj plugin](https://github.com/kana/vim-textobj-user/wiki).
- [wildfire.vim](https://github.com/gcmt/wildfire.vim).
- [targets.vim](https://github.com/wellle/targets.vim)

### File operations

- When current file needs to be moved, deleted [vim-eunuch](https://github.com/tpope/vim-eunuch)
- When some other file needs to be moved, deleted, could use file explorer like VimFiler or NerdTree.

### Git
- fugutive.vim.
- Recommend [gitv plugin](https://github.com/gregsexton/gitv), especially the **Gitv!** command of it is very useful! I love how it shows the evolution of the file through the commits :)
- **Vim-signify** is another must have plugin.

## TMUX

- Organize your workflow into sessions. If you are developing Rails project, create a rails session, when you are developing python project create a new python session. This [tmux-sessionist plugin](https://github.com/tmux-plugins/tmux-sessionist) is quite handy.

- Use [tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect) to save and load your sessions.

- Be familiar with the **prefix [** command (copymode in tmux). Currently using [tmux-copycat](https://github.com/tmux-plugins/tmux-copycat) and [tmux-open](https://github.com/tmux-plugins/tmux-open) is solving few of the navigation problem. I'm looking for project specific plugins, such as rails server or rspec related plugins, that could make it easier to navigate across the log to the errors or specific case.

- Check this [vim-tmux-navigator plugin](https://github.com/christoomey/vim-tmux-navigator) which also has a tmux conf. That conf is quite useful to switch easily.


## Git
- Avoid `git commit -m`, use `git commit`.
- Avoid `git add .` or `git add -A`, instead stage files individually and then commit.
- Avoid `git push -f`
- Avoid `git pull`, use `git pull --rebase` (or set it in your git config)
- Avoid pushing a `git rebase` branch  if it will be used by other users.
- Avoid making commits or pushes late. Commit often, push often.
- Avoid creating temporary branch when you need to quickly switch working on something else in your current branch. Use `git stash`
- Avoid resolving merge conflicts manually. Use `fugutive.vim` or use a good `mergetool`
