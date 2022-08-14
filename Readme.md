<header>
<img src="assets/abol.png" alt="logo" height="90" align="left">
<h1 style="display: inline">telesn.js</h1>

Modern Telegram Bot API framework for App Script

[![Bot API Version](https://img.shields.io/badge/Bot%20API-v6.0-f36caf.svg?style=flat-square)](https://core.telegram.org/bots/api)
![JavaScript](https://img.shields.io/github/languages/top/abdiu34567/Lost_and_Found)
[![Telesn](https://img.shields.io/badge/telesn-v1.0-f36caf.svg?style=flat-square)](https://core.telegram.org/bots/api)
[![English chat](https://img.shields.io/badge/English%20chat-grey?style=flat-square&logo=telegram)](https://t.me/App_Script_Js)

</header>

## Introduction

A Telegram bot is a program that offers functions and automations that Telegram users can integrate in their chats, channels, or groups

Telesn is a library that makes it simple for you to develop your own Telegram bots using JavaScript and [Apps Script](https://developers.google.com/apps-script)

### Features

- Simpler
- Full [Telegram Bot API 6.0](https://core.telegram.org/bots/api) support
- easier wirking across Google products
- per click Deployment on google cloud
- Real Time Database(Google sheet) already integrated

---

## **[Setting Up & Getting Started With Apps Script](https://github.com/abdiu34567/-Up-Coming-Framework/blob/main/GettingStartedAppScript.md)**

---

### Example

```js
const botUrl = Bot.Telesn(botToken)
Bot.setWebHook(webhookUrl)

function doPost(e) {
  const apiResponse = JSON.parse(e.postData.contents)
  let command = Bot.TextContents(apiResponse).text

  if (command == '/start') return Bot.reply('🎗 welcome ')
  if (command == '/help') return Bot.reply('🙏 Please help')
}
```
