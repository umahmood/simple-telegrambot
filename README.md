# Simple Telegram Bot

A simple python Telegram bot which sends and receives messages. Easy to use and 
easy to extend.

# Installation

> pip install simple-telegrambot

# Usage
```
# test-bot.py
from datetime import datetime, timezone

from simpletelegrambot import telegrambot

def on_message_receive(bot, message):
    utc_time = datetime.utcfromtimestamp(1504981128)
    msg_time = utc_time.strftime('%Y-%m-%d %H:%M:%S (UTC)')
    msg_text = message['text']

    print(msg_time, msg_text)

    if msg_text == 'Ping':
        bot.send_message('Pong')
    
def main():
    bot   = telegrambot.TelegramBot('<bot-token>')
    bot.set_message_handler(on_message_receive)
    bot.wait_for_messages()

if __name__ == '__main__':
    main()
```
Output:

```
$ python test_bot.py
2017-09-09 18:18:48 (UTC) Hello
2017-09-09 18:18:48 (UTC) Ping
```

# Testing

- python 3.6.3
- macOS 10.12.6 

# Dependencies

- [Requests 2.18.4](http://docs.python-requests.org/en/master/)

# License

See the [LICENSE](LICENSE.md) file for license rights and limitations (MIT).
