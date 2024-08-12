---
title: "A Friendly introduction to telegram bots api"
date: 2022-09-24T03:52:04+03:00
draft: true
---

# Telegram Bots

## A Friendly introduction to telegram bots api

a reply to bot A containing an explicit command for bot B or sent via bot C will only be available to bot A. Replies have the highest priority

- **Bot Father**

  the Bot father sends one status alerts per bot per hour

  Each alert has 3 buttons

  [1] - _Fixed_: use this if we fixed the problem from the alert.

  [2] - _Support_: use this to open a chat with [Bot Support](t.me/botsupport)

  [3] - _Mute for 8h/1w_: use this if we can't fix it now, this way we don't get status alert every hour

- **Privacy mode**

  only receives commands, replies to its messages and mentions.
  a Bot in a group and privacy mode only recieves.

  - messages that starts with `/`
  - replies to the bots own messages
  - services messages(people added or removed from the group)
  - messages from channels where it is a member

  _by default_ bots are in privacy mode, unless they are added as _admin_
  however we can get away without elevating the bot to admin, by using _ForceReply_ if necessary.
  **ForceReply** will ask the user to reply to the message, as if they selected the message and
  pressed the reply button. [More Read and Example](https://core.telegram.org/bots/api#forcereply)

- **Deep-Linking**

  allows for passing additional parameters to the bot on startup.

## Making Request

We can download and run the [Source Code](https://github.com/tdlib/telegram-bot-api) of the telegram api, and
run it in our own server, this comes with some benefits listed [here](https://core.telegram.org/bots/api#using-a-local-bot-api-server)

## Updates

Two ways of getting updates

[1] - Long Polling
[2] - Webhooks

The _getUpdates()_ method will return the last 100 unconfirmed updates.
to confirm an update, set the offset value to the last `update_id + 1`.
this will confirm the all the updates from the last getUpdates call, therefore these
updates will no longer be returned

## Dependancies

- [telebot-framwork](https://github.com/tucnak/telebot)

