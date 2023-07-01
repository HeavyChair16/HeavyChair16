from telethon.sync import TelegramClient, events

api_id = <your api_id>
api_hash = '<your api_hash>'

client = TelegramClient('session_name', api_id, api_hash)
client.start()

@client.on(events.NewMessage)
async def my_event_handler(event):
    await client.send_message(event.chat_id, 'Привет, я бот-мессенджер на Python!')

client.run_until_disconnected()
