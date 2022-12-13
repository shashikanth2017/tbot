# tbot
from turtle import update
from telegram.ext.updater import Updater
from telegram.update import Update
from telegram.ext.callbackcontext import CallbackContext
from telegram.ext.commandhandler import CommandHandler
from telegram.ext.messagehandler import MessageHandler
from telegram.ext.filters import Filters
from telegram import InputMediaPhoto


Updater=Updater("5438073881:AAElup0KsLpl5zuJ04WHsQD3_41mE_YKO2c",use_context=True)

def start(update:update,context:CallbackContext):

    update.message.reply_text("hey wass up? wanna explore something from shash write /help to see commands")
def help(update:update,context:CallbackContext):
    update.message.reply_text("""explorable spot
    /linkedin - for linkedin url
    /gmail - gmail url
    /image - image url
    /snapchat - snapchat url
    """)
def gmail_url(update: update,conetext:CallbackContext):
    update.message.reply_text("selvishashi117@gmail.com ")
def linkedIn_url(update: Update, context: CallbackContext):
    update.message.reply_text(
        "LinkedIn URL => \
        www.linkedin.com/in/shashi-kanth-299aa9206")
def snanchat_url(update: update,context:CallbackContext):
    update.message.reply_text("snapchat url => https://www.snapchat.com/add/shashhhh_2002?share_id=hl2Zdc9elxk&locale=en-GB  what you waitinn for just click and be part of shashh's snapchatters")
def image_url(update:Update, context:CallbackContext):
	  update.message.reply_text("currently found zero")
def unknown(update: Update, context: CallbackContext):
    update.message.reply_text(
        "Sorry '%s' is not a valid command" % update.message.text)
def unknown_text(update: Update, context: CallbackContext):
    update.message.reply_text(
        "oops, I can't get you , you said '%s'" % update.message.text)
Updater.dispatcher.add_handler(CommandHandler('start',start))   
Updater.dispatcher.add_handler(CommandHandler('help',help))
Updater.dispatcher.add_handler(CommandHandler('gmail',gmail_url))
Updater.dispatcher.add_handler(CommandHandler('linkedin',linkedIn_url))
Updater.dispatcher.add_handler(CommandHandler('snapchat',snanchat_url))
Updater.dispatcher.add_handler(CommandHandler('image',image_url,pass_args=True))
Updater.dispatcher.add_handler(MessageHandler(Filters.command,unknown))
Updater.dispatcher.add_handler(MessageHandler(Filters.text,unknown))
Updater.dispatcher.add_handler(MessageHandler(Filters.text,unknown_text))
Updater.start_polling()



