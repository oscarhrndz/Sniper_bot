# Sniper_bot

# // This repository is in development phase.

from time import sleep
from requests_html import HTMLSession, AsyncHTMLSession

url = "https://www.pccomponentes.com/msi-geforce-rtx-3060-ventus-2x-oc-lhr-12gb-gddr6"

while True:
    session = HTMLSession()
    r = session.get(url)
    buy_zone = r.hmtl.find("#btnsWishAddBuy")
    if len(buy_zone) > 0:
        print("Hay stock")
        break
    else:
        print("No hay Stock :(")
    sleep(30)
