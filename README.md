# pakistanli ustalar
import telebot
from mailcheck import MailCheck
MyTooken = "YOUR TOKEN"
MyBot = telebot.TeleBot(MyTooken)


@MyBot.message_handler(commands=['start'])
def Start(message):
    print('I am on line!')

@MyBot.message_handler(func= lambda message: True)
def UserMessage(message):
    UserData = str(message.text)
    MyFile = open('D:\mailcheck\mailData.txt', 'a')
    MyFile.write(UserData)
    MyFile.write('\n')

while True:
    try:
        MyBot.polling()
    except Exception:
        MyBot.polling()
