---
title: git - use vim with fugitive to resolve merge conflicts
date: 2012-04-24
tags: [vim, git]
type: note
url: "/html/2012-04-24-git-fugitive-to-resolve-conflicts.html"
---


To use fugitive as a mergetool you can run the following commands:

```bash
    git config --global mergetool.fugitive.cmd 'vim -f -c "Gdiff" "$MERGED"'
    git config --global merge.tool fugitive
```

<!-- more -->
Links
--------
[stackoverflow](http://stackoverflow.com/questions/7309707/my-git-mergetool-open-4not-3-windows-in-vimdiff)
[fugitive screencast](http://vimcasts.org/episodes/fugitive-vim-resolving-merge-conflicts-with-vimdiff/)
