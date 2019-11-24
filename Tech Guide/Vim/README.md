# **VIM Tutorial** (`$ vimtutor`)

## Chapter 0
- Personal configuration of VIM: `~/.vimrc` -> Check Chapter 7
- There are 3 stages in VIM:
  1. Command
  2. Insert = `i`
  3. View = `v`
- You can escape from each stage with `esc` button.
- Move cursor in command mode:
  - Left arrow = `h`
  - Right Arrow = `l`
  - Up Arrow = `k`
  - Down Arrow = `j`
- `Ctrl+b` = Page up
- `Ctrl+f` = Page down
- `:q` = [quit]
- `:q!` = [quit] without save
- `:qw` = [quit] with save
- `:w` = [write] save

## Chapter 1
- `a` = [append] -> start from a character 
- `x` = delete a character under the cursor
  - `xp` = substitute character under cursor with next character

## Chapter 2
- `d` = [Delete] + KEYWORD
  - `w` = [Word] + space
  - `e` = [End] -> from place of cursor to the end of word
  - `$` = to the end of line
- `w` = [Word] -> go to next word
- `e` = [End] -> go to end of word
- `0` or `^` = go to beginning of line
- `$` = go to end of line
- Combination (Operator[number]motion):
  - `d3w` = delete next 3 words
  - `d$` = delete whole line from cursor's position to the end of line
  - `ce` = [change] until the end of word + enter Insert mode
- `dd` = delete whole line without consideration of cursor's position
- `yy` = [Yank Yank] paste the deleted line in place of cursor
- `u` = [undo] undo a single character
- `U` = [Undo] undo a whole line changes
- `Ctrl+r` = [redo]

## Chapter 3
- `P` = [Put] previously deleted text under/after the cursor
- `rX` = [replace] replace the character under cursor with X

## Chapter 4
- `Ctrl+g` = show line numbers and your cursor's position
- `gg` = go to top of file
- `G` = go to end of file
- `NUM+G` = go to line number NUM
- `NUM+H` = go to NUMth line from top of screen
- `NUM+L` = go to NUMth line from bottom of screen
- Search
  - `/` = forward search
  - `?` = backward search
  - `n` = go to next word in search
  - `N` = go to previous word in search
  - `Ctrl+O` = go backward to where you came from
  - `Ctrl+I` = go forward from where you went with `Ctrl+O`
  - `/KEYWORD\c` = `\c` will ignore case sensitivity search for just a single time
- `%` = matching `(), {}, []` in current line
- Substitution
  - `:s/OLD/NEW` = To substitute NEW for the first OLD in a line
  - `:s/OLD/NEW/g` = To substitute NEW for all 'OLD's on a line
  - `:#,#s/OLD/NEW/g`
    - `#,#` = are line numbers. From line # to line #
    - `g` = globally (change all occurrences) in line
  - `:%s/OLD/NEW/g`
    - `%` = whole file without considering specific line numbers
  - `:%s/OLD/NEW/gc`
    - `c` = ask for confirmation whether to change it or not

## Chapter 5
- `:! COMMAND` = Execute the COMMAND with shell
- `:w FILENAME` = save this file to another file named FILENAME
- `v` = visual mode for selecting -> press `v` and select what you want with arrow keys, then press `:` and you can see `:'<,'>` on bottom. Finally you can decide what to do with your selection. For instance, you can save the selected part to another file and name it TEST. -> `:'<,'>w TEST`
- `V` = visual mode with line selection
- `Ctrl+v` = visual mode with block selection
- `:r FILENAME` = retrieves file FILENAME from your hard disk and puts it below the cursor position.
- `:r !COMMAND` = reads the output of your COMMAND and puts it below the cursor position.

## Chapter 6
- `o` = [open] a line below the cursor + enter Insert mode
- `O` = [Open] a line above the cursor + enter Insert mode
- Append commands
  - `a` = [append] from next character of cursor
  - `A` = [Append] from end of line
  - `i` = [insert] exactly at the place of cursor
- `R` = [Replace] mode is like insert mode, but every typed character deletes an existing character.
- Copy and Paste
  1. Select your text in visual mode (v)
  2. `y` = [yank] copy your selected text
  3. `p` = [paste] wherever you want

## Chapter 7
- `:help`
  - `Ctrl+w + Ctrl+w` = (Hold down Ctrl button and press w button 2 times) to jump from one window to another.
  - `:q` = close help window
- `:help KEYWORD` = find help on your KEYWORD
- VIMRC
  - Most of the vim features are disabled by default. You have to enable them manually by creating a configuration file named `vimrc`
  - If you wanna add plugins, remember that they are only load during initialization.
  - You can see example of `vimrc` with this command in vim `:r $VIMRUNTIME/vimrc_example.vim`
  - You can personalize your `vimrc` based on your programming language.
  - Some personal vimrc configurations:
    - `:set number` = show line numbers
    - `:set autoindent` = enable auto-indentation
    - `:set hlsearch` = enable highlight in search
    - `:set ic` = ignore case-sensitive in search
    - `:set is` = show partial matches for a search phrase
  - `:set noX` = You can disable set `X`
- Completion
  - `:set nocp` = To make sure Vim is not in compatible mode
  - Use `:` and choose a character, then press `Ctrl+d` to show a list of commands that start with your chosen character. You can even complete your command with `tab` button if it's unique.
  - It's pretty helpful in `:help` or large files which you need different commands to complete your work.