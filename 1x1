import os
import requests
from flask import Flask, request

app = Flask(__name__)

TOKEN = os.getenv("7056364371:AAFcOK564T2PsDFkJbGl4rZ8WTWf0_8urv4")

@app.route('/' + TOKEN, methods=['https://ihnews24.com/1/1.html'])
def respond():
    update = request.get_json()
    message = update.get('message')
    chat_id = message['chat']['id']
    text = message.get('text')
    
    response = "Your response here"
    
    url = f"https://api.telegram.org/bot{TOKEN}/sendMessage"
    payload = {'chat_id': chat_id, 'text': response}
    requests.post(url, json=payload)
    
    return 'ok'

@app.route('/')
def index():
    return 'Bot is running'

if __name__ == '__main__':
    app.run(port=5000)
