# slack-progress-bar
A Python library for adding a progress bar to a Slack Bot, updated for Python 3.9+.

![animated-gif](https://imgur.com/WkC70eR.gif)

## Installation
```bash
pip install slack-progress-bar
```

## Tutorial
1. Setup your bot using the Slack API and grab the associate bot `token`.
2. Get the `user_id` for the person you want to receive updates. This can be found by going to a Slack profile and clicking _Copy member ID_.
```python
import time
from slack_progress_bar import SlackProgressBar

progress_bar = SlackProgressBar(token=BOT_TOKEN, user_id=SLACK_MEMBER_ID, total=150)
for i in range(151):
   time.sleep(0.1)
   progress_bar.update(i)
```
Instantiating a `SlackProgressBar` will send a message to your Slack user featuring your empty progress bar.
Calling `update()` will update that progress bar on Slack.
To create a new progress bar, instantiate a new instance of `SlackProgressBar`.
