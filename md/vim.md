# Vim

---

## Mode

- insert
- normal
- visual
- command

---

### Insert mode

- i
  - insert before the char
- I
  - insert before the start of line
- a
  - append after the char
- A
  - append at the end of line

---

### Normal mode

- `<ESC>`

---

### Visual mode

- v
  - select a char
- V
  - select a line
- Ctrl + v
  - visual block mode

---

### Command mode

`:` + `<command>`

```vim
:wq
:cq
:set rnu
```

---

## Cursor movement

---

### Char

- h (left)
- j (down)
- k (up)
- l (right)
- Combile with number to move, `2k` to jump 2 lines up
- Relative line numbers `:set rnu`

---

### Word

- w or W
  - jump forwards to the start of a word
- e or E
  - jump forwards to the end of a word
- b or B
  - jump backwards to the start of a word
- Capital case can contain `punctuation`

---

### Single line

- $ - end of line
- ^ - start of the line after the indentation
- 0 - move to the column 0

---

### Move Cursor Q1

1. type `gg`
2. move to
```java
private final Tennis tennis = new Tennis("Miki", "Sing");
```
3. cursor move to the `p` on `private`
4. cursor move to the `e` on `private`

===

### Move Cursor Q2

1. type `G`
2. go to
```java
private void givenFirstPlayerScore(int times)
```
3. cursor go to `(`
4. cursor go to `)`

---

### Text Object motion

- {}
  - paragraphs forward/backward
- ()
  - sentences forward/backward
- []
  - backward/forward sections

---

### Pair

- %
  - go to the match bracket

---

### Screen

- H
  - move to top of screen
- M
  - move to middle of screen
- L
  - move to bottom of screen

---

### File

- gg
  - Start
- G
  - end of file
- :`<absolute-line-numbers>`
  - move to the absolute line

---

### Scroll

- zt
  - scroll current line to top
- zb
  - scroll current line to bottom
- zz
  - scroll current line to middle

---

## Search

---

### Search char in single line

- f/F
  - find char, forward/backward
  - `abcABCabc`, `fC` to find middle C
- t/T
  - Go to previous char before the char, forward/backward
  - `foo.bar<>` , move to r by `t<`
- ;
  - Repeat `t/T/f/F`
- ,
  - Reverse `t/T/f/F`

---

### Search char in single line - Q1

1. gg
2. Go to 
```java
import static org.assertj.core.api.Assertions.assertThat;
```
3. Move cursor to the first `.`
4. Move cursor to the next `.`
5. Move cursor to the next `.`
6. Move cursor to the previous `.`
7. Move cursor to the previous `.`

---

### Search char in single line - Q2

1. gg
2. Go to 
```java
tennis.firstPlayerScore();
```
3. Move cursor to the charater before `;`
4. Move cursor to the charater after `.`

---

### Search in file

- /
  - Search forward
- ?
  - Search backward
- n and N
  - next and previous
- *, #
  - search next/previous current word
  - The behavior is identical to /`word`

---

### Search in file - Q1

1. gg
2. find next `deuce`
3. find next `deuce`
4. find previous `deuce`

===

### Search in file - Q2

1. G
2. find previous `Sing`
3. find previous `Sing`
4. find next `Sing`

---

## Edit

- Undo/Redo
  - u / Ctrl+r

---

### Insert

- insert line before/after the current line
  - o, O
- join two line (keep mode)
  - J

---

### Copy

- y + motion
  - combine with any motion, e.g. `yt;` or `yw`
- yy = Y
  - yank (copy) the current line

---

### Paste from clipboard registry

- p
  - paste after

- P
  - paste before

---

### Insert,Copy,Paste - Q1

1. gg
2. go to 
   ```java
   scoreShouldBe("love all");
   ```
3. copy the line
4. paste before 
   ```java
   scoreShouldBe("fifteen love");
   ```
5. paste after 
   ```java
   scoreShouldBe("fifteen love");
   ```

===

### Insert,Copy,Paste - Q2

1. G
2. find `tennis.firstPlayerScore();`
3. in the next line, insert two empty lines
4. join the two lines to remove all empty lines
5. copy `tennis.firstPlayerScore();`
6. paste to next line

---

### Cut and switch to insert mode

- c + motion
  - Cut
- C
  - Cut to end of line
- s
  - Substitute the char under the cursor
- S
  - Substitube the line
- r
  - replace a char
- R
  - Enter the insert-replace mode

---

### Cut and keep in normal mode

- d
  - `d3j` or `3dd`
- D
  - Delete to end of the line
- dd
  - Delete the entire line
- x and X
  - delete and backspace

---

### Cut Q1

1. gg
2. find `Miki`
3. change to `Mery`
4. repeat all of them

===

### Cut Q2

1. G
2. find `second`
3. change to `third`
4. repeat all of them

===

### Cut Q3

1. G
2. find first `all`
3. remove `a`
4. remove `scoreShouldBe("love all");` and type `tennis`

===

### in / around

```bash
# edit neariest word inside symbol, e.g. }
ci}

# edit neariest word outside symbol, e.g. ]
ca]

# delete inside tag
dit

# replace word with yanked word
vi]p

```

---

### Repeat action

- repeat action
  - .

---

### Macro

- `q` + `a~z`
  - record macro to `a~z`
- `normal mode` + `q` to quit recording
- `@` + `a~z` to excute macro

---

### Bookmark

- `m` + `a~z`
  - bookmark current location to `a~z`
- ` + `a~z`
  - go to a~z bookmark
- \``
  - go to the last position

---

### [Registers](https://www.brianstorti.com/vim-registers/)

- `"` + `a~z` `0~9` `"+*/:%-`
  - `:reg` see all registers
  - `"` the default(unnamed) register
  - `0` the default register for `y`(yank)
  - `+`, `*` the system clipboard
  - `/` the latest search keyword
  - `:` the latest used command
  - `%` the current file path
  - `#` the last edited file

> "adw : delete the word and save to register `a`

===

### Registers - Advance

- `"0p` - paste from last yank
- Use the register in the `Search` and `Command mode`
  - `ctrl` + `r` + `<register>`

> `*:%s/<ctrl+r>//abc/gc` to replace the lastest search keyword(*) to `abc` with confirmation dialog

---

### Change multi line

1. `Ctrl + v` to enter `Visual block mode`
2. Move cursor to select lines that need to be edited
3. `Shift + i`
4. `#`
5. Esc

---

### More

```bash
# increase the first right number in the line
Ctrl + A

# decrease the first right number in the line
Ctrl + X

# Make a word uppercase
gUe

# Show Line numbers
:set number

# Set relative line number
:set rnu

# get recent command list
q:

# Replace word A with word B
:%s/A/B/g

```

---

## vim X IDE

---

### Setup

- Ideavim
  1. click the `V` icon on the right bottom corner
  2. open `~/.ideavimrc`
  3. edit and save

- [VScode](https://github.com/Asing1001/tennis-kata#setup-vscode-configs)

---

### Reference

- [vim doc](http://vimdoc.sourceforge.net/htmldoc/motion.html)
- [vim register](https://www.brianstorti.com/vim-registers/)
- [vim cheatsheet](https://vim.rtorr.com/)

---

### More...and more

- ctrl+o
  - previous jump position
- ctrl+i
  - next jump position
- g;
  - previous Change position
- g,
  - next Change position
