---
title: "Tmux: how to run the same command in multiple panes"
date: 2024-01-30
tags: [tmux]
type: note
url: "/html/2024-01-30-tmux-run-same-command-in-multiple-panes.html"
---

# Why run the same command in multiple tmux panes?

Sometimes it can be convenient as a quick way to run some command in parallel on the server. We can still see the output, detach from tmux and disconnect
and reconnect later and attach to the tmux session to see the result.

# How to run the same command in multiple panes?

To run the same command in multiple panes, we can use a script like this:

```bash
#!/bin/bash

SESS='generation-jobs'
CMD='sleep 1 && echo "Hello, World\!"'
NUM_PANES=9 # 10 panes

# Create a new session named "$SESS"
tmux new-session -d -s $SESS

# Split the window into NUM_PANES panes
for i in $(seq 1 $NUM_PANES); do
  tmux split-window -v -t $SESS
  # Re-layout panes to be equally sized
  tmux select-layout -t $SESS tiled
done

# Set pane synchronization
tmux set-window-option -t $SESS:1 synchronize-panes on
# Run command in all panes
tmux send-keys -t $SESS "$CMD" Enter
# Attach to session named "$SESS"
tmux attach -t $SESS
```

It will work like this:

{{< video src="2024-01-30-tmux-run-same-command-in-multiple-panes.mp4" type="video/mp4">}}
