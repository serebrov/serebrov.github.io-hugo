---
title: vim - replace a word with yanked text
date: 2012-04-03
tags: [vim]
type: note
url: "/html/2012-04-03-vim-replace-word-with-yanked-text.html"
---

To replace a word (or other text) with a text from the clipboard, select the new text and then paste clipboard version over:

* Yank inner word: `yiw`
* Move cursor to another word
* Select it and paste over: `viwp`
* If you need to replace more words:
  * Option 1: `gvy` to reselect and copy pasted word then do `viwp` on another word
  * Option 2: use `viw"0p` on another word, here `"0p` will paste from `0` register (the default register will contain previously replaced word)


<!-- more -->
Deleting, changing and yanking text copies the affected text to the unnamed register ("").

Yanking text also copies the text to register 0 ("0).

So the command `yiw` copies the current word to `""` and to `"0`.

Typing `viw` selects the current word, then pressing `p` pastes the unnamed register over the visual selection.
The visual selection is deleted to the unnamed register.

Links
------
[vim.wikia.com](http://vim.wikia.com/wiki/Replace_a_word_with_yanked_text)
