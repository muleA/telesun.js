## forwardMessage

> Use this method to forward messages of any kind. Service messages can't be forwarded. On success, the sent Message is returned
>
> For more check [forwardMessage](https://core.telegram.org/bots/api#forwardmessage) method
>
> parameters :
>
> - chat_id `required`
> - from_chat_id `required`
> - message_id `required`
> - disable_notification = false
> - protect_content = false

> forwarding message directly, without any request, use this for `test` purposes , because of this can be done without any `deployment`

```js
Bot.Telesun(botToken)

// create and run function like this if only you know chat id of the user.

//forwarding from @ab_trial group to @app_Script_js group
function forwardMessageToChannelorgroup() {
  let channelOrGroupUserName = '@App_Script_Js'
  let originalChannelOrGoup = '@ab_trial'
  let msg_idOfOriginalMessage = 234
  return Bot.forwardMessage(
    channelOrGroupUserName,
    originalChannelOrGoup,
    msg_idOfOriginalMessage
  )
}

//forwarding from userDeva to userAbdi group
function forwardMessageToBot() {
  let userAbdi = '1173180004'
  let userDeva = '1263669270'
  let msg_idOfOriginalMessage = 234
  return Bot.forwardMessage(userAbdi, userDeva, msg_idOfOriginalMessage)
}

//forwarding from userAbdi to App script channel
function forwardMessageFromBotToGroupOrChannel() {
  let channelOrGroupUserName = '@App_Script_Js'
  let userAbdi = '1173180004'
  let msg_idOfOriginalMessage = 234
  return Bot.forwardMessage(
    channelOrGroupUserName,
    userAbdi,
    msg_idOfOriginalMessage
  )
}
```

> forwarding message on webhook

```js
Bot.Telesun(botToken)

function doPost(e) {
  const apiResponse = JSON.parse(e.postData.contents)
  let myChatId = Bot.TextContents(apiResponse).id
  let originalChannel = '@App_Script_Js'
  let originalMsgId = 232

  return Bot.forwardMessage(myChatId, originalChannel, originalMsgId)
}
```
