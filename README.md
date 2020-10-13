# daily-dev-cheatsheet
Aggregation of some cheatsheets I use on a daily basis

## Git - https://training.github.com/downloads/github-git-cheat-sheet/

### Configure tooling
Configure user information for all local repositories

`$ git config --global user.name "[name]"`

Sets the name you want attached to your commit transactions

`$ git config --global user.email "[email address]"`

Sets the email you want attached to your commit transactions

`$ git config --global color.ui auto`

Enables helpful colorization of command line output

### Branches
Branches are an important part of working with Git. Any commits you make will be made on the branch you’re currently “checked out” to. Use git status to see which branch that is.

`$ git branch [branch-name]`

Creates a new branch

`$ git checkout [branch-name]`

Switches to the specified branch and updates the working directory

`$ git merge [branch]`

Combines the specified branch’s history into the current branch. This is usually done in pull requests, but is an important Git operation.

`$ git branch -d [branch-name]`

Deletes the specified branch

### Create repositories
When starting out with a new repository, you only need to do it once; either locally, then push to GitHub, or by cloning an existing repository.

`$ git init`

After using the git init command, link the local repository to an empty GitHub repository using the following command:

`$ git remote add origin [url]`

Turn an existing directory into a Git repository

$ git clone [url]

Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits

The .gitignore file
Sometimes it may be a good idea to exclude files from being tracked with Git. This is typically done in a special file named .gitignore. You can find helpful templates for .gitignore files at github.com/github/gitignore.

### Synchronize changes
Synchronize your local repository with the remote repository on GitHub.com

`$ git fetch`

Downloads all history from the remote tracking branches

`$ git merge`

Combines remote tracking branches into current local branch

`$ git push`

Uploads all local branch commits to GitHub

`$ git pull`

Updates your current local working branch with all new commits from the corresponding remote branch on GitHub. git pull is a combination of git fetch and git merge

### Make changes
Browse and inspect the evolution of project files

`$ git log`

Lists version history for the current branch

`$ git log --follow [file]`

Lists version history for a file, including renames

`$ git diff [first-branch]...[second-branch]`

Shows content differences between two branches

`$ git show [commit]`

Outputs metadata and content changes of the specified commit

`$ git add [file]`

Snapshots the file in preparation for versioning

`$ git commit -m "[descriptive message]"`

Records file snapshots permanently in version history

### Redo commits
Erase mistakes and craft replacement history

`$ git reset [commit]`

Undoes all commits after [commit], preserving changes locally

`$ git reset --hard [commit]`

Discards all history and changes back to the specified commit

## Vim - https://github.com/rstacruz/cheatsheets/blob/master/vim.mde

General Vim Tips: http://zzapper.co.uk/vimtips.html

### Exiting

| Shortcut       | Description                      |
| -------------- | -------------------------------- |
| `:qa`          | Close all files                  |
| `:qa!`         | Close all files, abandon changes |
| ---            | ---                              |
| `:w`           | Save                             |
| `:wq` _/_ `:x` | Save and close file              |
| ---            | ---                              |
| `:q`           | Close file                       |
| `:q!`          | Close file, abandon changes      |
| ---            | ---                              |
| `ZZ`           | Save and quit                    |
| `ZQ`           | Quit without checking changes    |

### Navigating

| Shortcut            | Description       |
| ---                 | ---               |
| `h` `j` `k` `l`     | Arrow keys        |
| `<C-U>` _/_ `<C-D>` | Half-page up/down |
| `<C-B>` _/_ `<C-F>` | Page up/down      |

#### Words

| Shortcut     | Description               |
| ---          | ---                       |
| `b` _/_ `w`  | Previous/next word        |
| `ge` _/_ `e` | Previous/next end of word |

#### Line

| Shortcut     | Description                        |
| ---          | ---                                |
| `0` _(zero)_ | Start of line                      |
| `^`          | Start of line _(after whitespace)_ |
| `$`          | End of line                        |

#### Character

| `fc`  | Go forward to character `c`  |
| `Fc`  | Go backward to character `c` |

#### Document

| Shortcut | Description    |
| ---      | ---            |
| `gg`     | First line     |
| `G`      | Last line      |
| `:n`     | Go to line `n` |
| `nG`     | Go to line `n` |

#### Window

| Shortcut | Description              |
| ---      | ---                      |
| `zz`     | Center this line         |
| `zt`     | Top this line            |
| `zb`     | Bottom this line         |
| `H`      | Move to top of screen    |
| `M`      | Move to middle of screen |
| `L`      | Move to bottom of screen |

#### Search

| Shortcut  | Description                         |
| ---       | ---                                 |
| `n`       | Next matching search pattern        |
| `N`       | Previous match                      |
| `*`       | Next whole word under cursor        |
| `#`       | Previous whole word under cursor    |

#### Tab pages

| Shortcut              | Description                     |
| ---                   | ---                             |
| `:tabedit [file]`     | Edit file in a new tab          |
| `:tabfind [file]`     | Open file if exists in new tab  |
| `:tabclose`           | Close current tab               |
| `:tabs`               | List all tabs                   | 
| `:tabfirst`           | Go to first tab                 |
| `:tablast`            | Go to last tab                  |
| `:tabn    `           | Go to next tab                  |
| `:tabp    `           | Go to previous tab              |

### Editing

| Shortcut | Description                         |
| ---      | ---                                 |
| `a`      | Append                              |
| `A`      | Append from end of line             |
| `i`      | Insert                              |
| `o`      | Next line                           |
| `O`      | Previous line                       |
| ---      | ---                                 |
| `s`      | Delete char and insert              |
| `S`      | Delete line and insert              |
| `C`      | Delete until end of line and insert |
| ---      | ---                                 |
| `r`      | Replace one character               |
| `R`      | Enter Replace mode                  |
| ---      | ---                                 |
| `u`      | Undo changes                        |
| `<C-R>`  | Redo changes                        |

### Exiting insert mode

| Shortcut          | Description |
| ---               | ---         |
| `Esc` _/_ `<C-[>` | Exit insert mode |
| `<C-C>`           | Exit insert mode, and abort current command |

### Clipboard

| Shortcut        | Description                 |
| ---             | ---                         |
| `x`             | Delete character            |
| ---             | ---                         |
| `dd`            | Delete line _(Cut)_         |
| `yy`            | Yank line _(Copy)_          |
| ---             | ---                         |
| `p`             | Paste                       |
| `P`             | Paste before                |
| ---             | ---                         |
| `"*p` _/_ `"+p` | Paste from system clipboard |
| `"*y` _/_ `"+y` | Paste to system clipboard   |

### Visual mode

| Shortcut | Description             |
| ---      | ---                     |
| `v`      | Enter visual mode       |
| `V`      | Enter visual line mode  |
| `<C-V>`  | Enter visual block mode |

#### In visual mode

| Shortcut    | Description             |
| ---         | ---                     |
| `d` _/_ `x` | Delete selection        |
| `s`         | Replace selection       |
| `y`         | Yank selection _(Copy)_ |
{: .-shortcuts}

See [Operators](#operators) for other things you can do.

Operators
---------

### Usage

Operators let you operate in a range of text (defined by *motion*). These are performed in normal mode.
{: .-setup}

| `d`      | `w`    |
| Operator | Motion |

### Operators list

| Shortcut | Description                     |
| ---      | ---                             |
| `d`      | Delete                          |
| `y`      | Yank _(copy)_                   |
| `c`      | Change _(delete then insert)_   |
| ---      | ---                             |
| `>`      | Indent right                    |
| `<`      | Indent left                     |
| `=`      | Autoindent                      |
| ---      | ---                             |
| `g~`     | Swap case                       |
| `gU`     | Uppercase                       |
| `gu`     | Lowercase                       |
| ---      | ---                             |
| `!`      | Filter through external program |

See `:help operator`

### Examples

Combine operators with *motions* to use them.

| Shortcut               | Description                               |
| ---                    | ---                                       |
| `d`_d_                 | _(repeat the letter)_ Delete current line |
| `d`_w_                 | Delete to next word                       |
| `d`_b_                 | Delete to beginning of word               |
| _2_`dd`                | Delete 2 lines                            |
| `d`_ip_                | Delete a text object _(inside paragraph)_ |
| _(in visual mode)_ `d` | Delete selection                          |

See: `:help motion.txt`

Text objects
------------

### Usage

Text objects let you operate (with an *operator*) in or around text blocks (*objects*).
{: .-setup}

| `v`      | `i`                  | `p`         |
| Operator | [i]nside or [a]round | Text object |
{: .-css-breakdown}

### Text objects

| Shortcut               | Description           |
| ---                    | ---                   |
| `p`                    | Paragraph             |
| `w`                    | Word                  |
| `s`                    | Sentence              |
| ---                    | ---                   |
| `[` `(` `{` `<`        | A [], (), or {} block |
| `'` `"` <code>`</code> | A quoted string       |
| ---                    | ---                   |
| `b`                    | A block [(            |
| `B`                    | A block in [{         |
| `t`                    | A XML tag block       |
{: .-shortcuts}

### Examples

| Shortcut    | Description                        |
| ---         | ---                                |
| `vip`       | Select paragraph                   |
| `vipipipip` | Select more                        |
| ---         | ---                                |
| `yip`       | Yank inner paragraph               |
| `yap`       | Yank paragraph (including newline) |
| ---         | ---                                |
| `dip`       | Delete inner paragraph             |
| `cip`       | Change inner paragraph             |

See [Operators](#operators) for other things you can do.

### Diff
 
| Shortcut                             | Description                              |
| ---                                  | ---                                      |
| `gvimdiff file1 file2 [file3]`       | See differences between files, in HMI    |
 

Misc
----

### Folds

| Shortcut      | Description                  |
| ---           | ---                          |
| `zo` _/_ `zO` | Open                         |
| `zc` _/_ `zC` | Close                        |
| `za` _/_ `zA` | Toggle                       |
| ---           | ---                          |
| `zv`          | Open folds for this line     |
| ---           | ---                          |
| `zM`          | Close all                    |
| `zR`          | Open all                     |
| ---           | ---                          |
| `zm`          | Fold more _(foldlevel += 1)_ |
| `zr`          | Fold less _(foldlevel -= 1)_ |
| ---           | ---                          |
| `zx`          | Update folds                 |

Uppercase ones are recursive (eg, `zO` is open recursively).

### Navigation

| Shortcut            | Description                |
| ---                 | ---                        |
| `%`                 | Nearest/matching `{[()]}`  |
| `[(` `[{` `[<`      | Previous `(` or `{` or `<` |
| `])`                | Next                       |
| ---                 | ---                        |
| `[m`                | Previous method start      |
| `[M`                | Previous method end        |

### Jumping

| Shortcut | Description                  |
| ---      | ---                          |
| `<C-O>`  | Go back to previous location |
| `<C-I>`  | Go forward                   |
| ---      | ---                          |
| `gf`     | Go to file in cursor         |

### Counters

| Shortcut | Description      |
| ---      | ---              |
| `<C-A>`  | Increment number |
| `<C-X>`  | Decrement        |

### Windows

| `z{height}<Cr>` | Resize pane to `{height}` lines tall |

### Tags

| Shortcut              | Description                                     |
| ---                   | ---                                             |
| `:tag Classname`      | Jump to first definition of Classname           |
| ---                   | ---                                             |
| `<C-]>`               | Jump to definition                              |
| `g]`                  | See all definitions                             |
| `<C-T>`               | Go back to last tag                             |
| `<C-O> <C-I>`         | Back/forward                                    |
| ---                   | ---                                             |
| `:tselect Classname`  | Find definitions of Classname                   |
| `:tjump Classname`    | Find definitions of Classname (auto-select 1st) |
{: .-shortcuts}

### Case

| Shortcut | Description                          |
| ---      | ---                                  |
| `~`      | Toggle case (Case => cASE)           |
| `gU`     | Uppercase                            |
| `gu`     | Lowercase                            |
| ---      | ---                                  |
| `gUU`    | Uppercase current line (also `gUgU`) |
| `guu`    | Lowercase current line (also `gugu`) |
{: .-shortcuts}

Do these in visual or normal mode.

### Marks

| Shortcut           | Description                                          |
| ---                | ---                                                  |
| <code>`^</code>    | Last position of cursor in insert mode               |
| <code>`.</code>    | Last change in current buffer                        |
| <code>`"</code>    | Last exited current buffer                           |
| <code>`0</code>    | In last file edited                                  |
| <code>''</code>    | Back to line in current buffer where jumped from     |
| <code>``</code>    | Back to position in current buffer where jumped from |
| <code>`[</code>    | To beginning of previously changed or yanked text    |
| <code>`]</code>    | To end of previously changed or yanked text          |
| <code>`&lt;</code> | To beginning of last visual selection                |
| <code>`&gt;</code> | To end of last visual selection                      |
| ---                | ---                                                  |
| `ma`               | Mark this cursor position as `a`                     |
| <code>`a</code>    | Jump to the cursor position `a`                      |
| `'a`               | Jump to the beginning of the line with position `a`  |
| <code>d'a</code>   | Delete from current line to line of mark `a`         |
| <code>d`a</code>   | Delete from current position to position of mark `a` |
| <code>c'a</code>   | Change text from current line to line of `a`         |
| <code>y`a</code>   | Yank text from current position to position of `a`   |
| ---                | ---                                                  |
| `:marks`           | List all current marks                               |
| `:delm a`          | Delete mark `a`                                      |
| `:delm a-d`        | Delete marks `a`, `b`, `c`, `d`                      |
| `:delm abc`        | Delete marks `a`, `b`, `c`                           |

### Misc

| Shortcut   | Description                                       |
| ---        | ---                                               |
| `.`        | Repeat last command                               |
| `]p`       | Paste under the current indentation level         |
| ---        | ---                                               |
| `:set ff=unix` | Convert Windows line endings to Unix line endings |

### Command line

| Shortcut     | Description                               |
| ---          | ---                                       |
| `<C-R><C-W>` | Insert current word into the command line |
| `<C-R>"`     | Paste from " register                     |
| `<C-X><C-F>` | Auto-completion of path in insert mode    |

### Text alignment

    :center [width]
    :right [width]
    :left

See `:help formatting`

### Calculator

| Shortcut      | Description                               |
| ---           | ---                                       |
| `<C-R>=128/2` | Shows the result of the division : '64'   |

Do this in insert mode.

### Exiting with an error

    :cq
    :cquit

Works like `:qa`, but throws an error. Great for aborting Git commands.


### Spell checking

| Shortcut                     | Description                                             |
| ---                          | ---                                                     |
| `:set spell spelllang=en_us` | Turn on US English spell checking                       |
| `]s`                         | Move to next misspelled word after the cursor           |
| `[s`                         | Move to previous misspelled word before the cursor      |
| `z=`                         | Suggest spellings for the word under/after the cursor   |
| `zg`                         | Add word to spell list                                  |
| `zw`                         | Mark word as bad/mispelling                             |
| `zu` / `C-X (Insert Mode)`   | Suggest words for bad word under cursor from spellfile  |
{: .-shortcuts}

See `:help spell`

### Tmux - https://gist.github.com/MohamedAlaa/2961058

start new:

    tmux

start new with session name:

    tmux new -s myname

attach:

    tmux a  #  (or at, or attach)

attach to named:

    tmux a -t myname

list sessions:

    tmux ls

<a name="killSessions"></a>kill session:

    tmux kill-session -t myname

<a name="killAllSessions"></a>Kill all the tmux sessions:

    tmux ls | grep : | cut -d. -f1 | awk '{print substr($1, 0, length($1)-1)}' | xargs kill

In tmux, hit the prefix `ctrl+b` (my modified prefix is ctrl+a) and then:

## List all shortcuts
to see all the shortcuts keys in tmux simply use the `bind-key ?` in my case that would be `CTRL-B ?`

## Sessions

    :new<CR>  new session
    s  list sessions
    $  name session

## <a name="WindowsTabs"></a>Windows (tabs)

    c  create window
    w  list windows
    n  next window
    p  previous window
    f  find window
    ,  name window
    &  kill window

## <a name="PanesSplits"></a>Panes (splits) 

    %  vertical split
    "  horizontal split
    
    o  swap panes
    q  show pane numbers
    x  kill pane
    +  break pane into window (e.g. to select text by mouse to copy)
    -  restore pane from window
    ⍽  space - toggle between layouts
    <prefix> q (Show pane numbers, when the numbers show up type the key to goto that pane)
    <prefix> { (Move the current pane left)
    <prefix> } (Move the current pane right)
    <prefix> z toggle pane zoom

## <a name="syncPanes"></a>Sync Panes 

You can do this by switching to the appropriate window, typing your Tmux prefix (commonly Ctrl-B or Ctrl-A) and then a colon to bring up a Tmux command line, and typing:

```
:setw synchronize-panes
```

You can optionally add on or off to specify which state you want; otherwise the option is simply toggled. This option is specific to one window, so it won’t change the way your other sessions or windows operate. When you’re done, toggle it off again by repeating the command. [tip source](http://blog.sanctum.geek.nz/sync-tmux-panes/)


## Resizing Panes

You can also resize panes if you don’t like the layout defaults. I personally rarely need to do this, though it’s handy to know how. Here is the basic syntax to resize panes:

    PREFIX : resize-pane -D (Resizes the current pane down)
    PREFIX : resize-pane -U (Resizes the current pane upward)
    PREFIX : resize-pane -L (Resizes the current pane left)
    PREFIX : resize-pane -R (Resizes the current pane right)
    PREFIX : resize-pane -D 20 (Resizes the current pane down by 20 cells)
    PREFIX : resize-pane -U 20 (Resizes the current pane upward by 20 cells)
    PREFIX : resize-pane -L 20 (Resizes the current pane left by 20 cells)
    PREFIX : resize-pane -R 20 (Resizes the current pane right by 20 cells)
    PREFIX : resize-pane -t 2 20 (Resizes the pane with the id of 2 down by 20 cells)
    PREFIX : resize-pane -t -L 20 (Resizes the pane with the id of 2 left by 20 cells)
    
    
## Copy mode:

Pressing PREFIX [ places us in Copy mode. We can then use our movement keys to move our cursor around the screen. By default, the arrow keys work. we set our configuration file to use Vim keys for moving between windows and resizing panes so we wouldn’t have to take our hands off the home row. tmux has a vi mode for working with the buffer as well. To enable it, add this line to .tmux.conf:

    setw -g mode-keys vi

With this option set, we can use h, j, k, and l to move around our buffer.

To get out of Copy mode, we just press the ENTER key. Moving around one character at a time isn’t very efficient. Since we enabled vi mode, we can also use some other visible shortcuts to move around the buffer.

For example, we can use "w" to jump to the next word and "b" to jump back one word. And we can use "f", followed by any character, to jump to that character on the same line, and "F" to jump backwards on the line.

       Function                vi             emacs
       Back to indentation     ^              M-m
       Clear selection         Escape         C-g
       Copy selection          Enter          M-w
       Cursor down             j              Down
       Cursor left             h              Left
       Cursor right            l              Right
       Cursor to bottom line   L
       Cursor to middle line   M              M-r
       Cursor to top line      H              M-R
       Cursor up               k              Up
       Delete entire line      d              C-u
       Delete to end of line   D              C-k
       End of line             $              C-e
       Goto line               :              g
       Half page down          C-d            M-Down
       Half page up            C-u            M-Up
       Next page               C-f            Page down
       Next word               w              M-f
       Paste buffer            p              C-y
       Previous page           C-b            Page up
       Previous word           b              M-b
       Quit mode               q              Escape
       Scroll down             C-Down or J    C-Down
       Scroll up               C-Up or K      C-Up
       Search again            n              n
       Search backward         ?              C-r
       Search forward          /              C-s
       Start of line           0              C-a
       Start selection         Space          C-Space
       Transpose chars                        C-t

## Misc

    d  detach
    t  big clock
    ?  list shortcuts
    :  prompt

## Configurations Options:

    # Mouse support - set to on if you want to use the mouse
    * setw -g mode-mouse off
    * set -g mouse-select-pane off
    * set -g mouse-resize-pane off
    * set -g mouse-select-window off

    # Set the default terminal mode to 256color mode
    set -g default-terminal "screen-256color"

    # enable activity alerts
    setw -g monitor-activity on
    set -g visual-activity on

    # Center the window list
    set -g status-justify centre

    # Maximize and restore a pane
    unbind Up bind Up new-window -d -n tmp \; swap-pane -s tmp.1 \; select-window -t tmp
    unbind Down
    bind Down last-window \; swap-pane -s tmp.1 \; kill-window -t tmp

## Resources:

* [tmux: Productive Mouse-Free Development](http://pragprog.com/book/bhtmux/tmux)
* [How to reorder windows](http://superuser.com/questions/343572/tmux-how-do-i-reorder-my-windows)
