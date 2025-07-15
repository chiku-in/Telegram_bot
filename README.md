import telebot
import os

TOKEN = os.environ.get("7939283864:AAHAdSfxSO44fNupUfPuik8clPgfznDfLw4")  # Environment variable से टोकन

bot = telebot.TeleBot(TOKEN)

@bot.message_handler(commands=['start'])
def send_welcome(message):
    bot.reply_to(message, "Hello! Railway से चला हूँ 🤖")

@bot.message_handler(func=lambda message: True)
def echo_all(message):
    bot.reply_to(message, message.text)

bot.polling()
