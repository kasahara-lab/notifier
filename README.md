# Notifier
When you run a long-running job on a Linux cluster or an HPC environment,
you wish to be notified when your job finishes. One way to do that is
you set up Notifier to let you know when your job is finished.
This is particularly useful when you wish to be notified only in daytime;
Slack lets you customize when to get notifications and when not to.

# Setting up
You create a following config file at `~/.config/notifier/notifierrc`,
assuming the channel name of Slack to which you wish to send messages
is `hpcjobs`:

```
[slack]
hpcjobs='https://hooks.slack.com/services/abc/AB0123445/AB0123CDE456/bQ2CbS5DfFDSfsafadbFJ'
```

The URL after the `hpcjobs=` is the webhook URL of the channel.
Please see [Sending messages using Incoming Webhooks](https://api.slack.com/messaging/webhooks)
for details of how to set up a webhook for a Slack channel.

# Sending a message
Here, we assume that `notifier` is somewhere on your PATH.

When you wish to send the following message to `hpcjobs` channel you defined in `notifierrc`:
```
$ notifier -c hpcjobs "Job succeeded\!"
```

When you wish to send the following message to `test` channel you defined in `notifierrc`:
```
$ notifier -c test "Job failed."
```

# LICENSE
MIT
