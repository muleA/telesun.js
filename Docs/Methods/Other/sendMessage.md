## sendMessage

> Use this method to send text messages. On success, the sent Message is returned.
>
> For more check [sendMessage](https://core.telegram.org/bots/api#sendmessage) method
>
> parameters :
>
> - chat_id `required`
> - text `required`
> - parse_mode = 'HTML'
> - reply_markup
> - entities
> - disable_web_page_preview = false
> - disable_notification = false
> - protect_content = false
> - reply_to_message_id
> - allow_sending_without_reply = false
>
> For parameters like `caption_entities`, `reply_markup` check [Types](https://github.com/abdiu34567/telesn.js/tree/main/Docs/Types)
>
> sending message directly, without any request, use this for `test` purposes , because of this can be done without any `deployment`

```js
Bot.Telesun(botToken)

// create and run function like this if only you know chat id of the user or username of channel(group).

// this function will send 'hello some one' message to 1173180004 (user)
function sendMessageToBot() {
  let someOneChatId = '1173180004'
  return Bot.sendMessage(someOneChatId, 'Hello Some One')
}

//The bot have to be member of the Group or channel
function sendMessageToChannelOrGroup() {
  let channelorGroupUserName = '@App_Script_Js'
  return Bot.sendMessage(channelorGroupUserName, 'Hello members')
}
```

> sending message on webhook

```js
Bot.Telesun(botToken)

function doPost(e) {
  const apiResponse = JSON.parse(e.postData.contents)

  //accessing user chat id from the API
  let myChatId = Bot.TextContents(apiResponse).id

  return Bot.sendMessage(myChatId, ' Hello Who ever Using This Bot')
}
```

> applying all 10 parameters
>
> you can use `undefined` data type for all optional paramaters (never use `null`)

```js

Bot.Telesn(botToken)
Bot.setWebHook(webhookUrl)

function doPost(e) {
  const apiResponse = JSON.parse(e.postData.contents)

  //accessing user chat id from the API
  let chatId = Bot.TextContents(apiResponse).id


  let inlinekeyboard = {
  "inline_keyboard": [
    [{
      "text": "Number",
      "callback_data": "number"
    }], [{
      "text": "String",
      "callback_data": "string"
    }]
  ]
}

  let entities = [{
    type: 'mention',
    offset:0,
    length:10
    }]

  return Bot.sendMessage(
    chatId,
    '**JavaScript data types**',
    'MarkdownV2',
    inlinekeyboard,
    entities,
    true,
    true,
    true,
    322,//msg_Id
    true
  )
```
