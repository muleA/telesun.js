## File contents **Photo**

> already defined in the library
>
> This can be accessible when user send any `photo` to bot

```js
//this function is already defined in the library, you just need to call it on doPost function
function PhotoContents(apiResponse) {
  return {
    name: apiResponse.message.from.first_name,
    photo: apiResponse.message.photo.file_id,
    id: apiResponse.message.from.id,
    username: apiResponse.message.from.username,
    msgid: apiResponse.message.message_id,
  }
}
```

> using `PhotoContents` function on from library on your `dopost` function

```js
// use this way on dopost() function
let chatId = PhotoContents(apiResponse).id
let text = PhotoContents(apiResponse).text
```

> Coming Api `Example`

```js

{
  "update_id": 144178483,
  "message": {
    "message_id": 661256,
    "from": {
      "id": 1173180004,
      "is_bot": false,
      "first_name": "Me",
      "last_name": "ab",
      "username": "Me_abd",
      "language_code": "en"
    },
    "chat": {
      "id": 1173180004,
      "first_name": "Me",
      "last_name": "ab",
      "username": "Me_abd",
      "type": "private"
    },
    "date": 1661022177,
    "photo": [
      {
        "file_id": "AgACAgQAAxkBAAEKFwhjAS_h1y-zTDDnlgnrGyVCwZbDpwAC07oxG8DtCFDu8bAwUwyBJAEAAwIAA3MAAykE",
        "file_unique_id": "AQAD07oxG8DtCFB4",
        "file_size": 2213,
        "width": 78,
        "height": 90
      },
      {
        "file_id": "AgACAgQAAxkBAAEKFwhjAS_h1y-zTDDnlgnrGyVCwZbDpwAC07oxG8DtCFDu8bAwUwyBJAEAAwIAA20AAykE",
        "file_unique_id": "AQAD07oxG8DtCFBy",
        "file_size": 32005,
        "width": 278,
        "height": 320
      },
      {
        "file_id": "AgACAgQAAxkBAAEKFwhjAS_h1y-zTDDnlgnrGyVCwZbDpwAC07oxG8DtCFDu8bAwUwyBJAEAAwIAA3kAAykE",
        "file_unique_id": "AQAD07oxG8DtCFB-",
        "file_size": 87891,
        "width": 720,
        "height": 829
      },
      {
        "file_id": "AgACAgQAAxkBAAEKFwhjAS_h1y-zTDDnlgnrGyVCwZbDpwAC07oxG8DtCFDu8bAwUwyBJAEAAwIAA3gAAykE",
        "file_unique_id": "AQAD07oxG8DtCFB9",
        "file_size": 131280,
        "width": 695,
        "height": 800
      }
    ]
  }
}
```
