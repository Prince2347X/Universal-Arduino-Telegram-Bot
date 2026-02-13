# Reply To Message Example

This example demonstrates how to use the `reply_to_message_id` parameter to reply to specific messages in a Telegram chat.

## What it does

When you send a message to the bot, it will reply to your message (quoting it in Telegram). This creates a conversation thread where the bot's response is linked to your original message.

## How it works

The bot uses the `message_id` from the received message and passes it as the `reply_to_message_id` parameter when sending a response:

```cpp
int message_id = bot.messages[i].message_id;
bot.sendMessage(chat_id, "You said: " + text, "", 0, message_id);
```

The last parameter (`message_id` value) is passed to the `reply_to_message_id` parameter of `sendMessage()`, which tells Telegram to reply to that specific message.

## Usage

1. Configure your WiFi credentials and bot token
2. Upload the sketch to your ESP8266
3. Send any message to your bot
4. The bot will reply to your message, showing the quote/reference in Telegram

## Additional Features

The `reply_to_message_id` parameter is available in all message-sending methods:
- `sendMessage()`
- `sendSimpleMessage()`
- `sendMessageWithReplyKeyboard()`
- `sendMessageWithInlineKeyboard()`
- `sendPhoto()`
