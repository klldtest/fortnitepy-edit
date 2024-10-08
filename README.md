 # fortnitepy-edit

[![Supported py versions](https://img.shields.io/pypi/pyversions/fortnitepy-edit.svg)](https://pypi.org/project/fortnitepy-edit/)
[![Current pypi version](https://img.shields.io/pypi/v/fortnitepy-edit.svg)](https://pypi.org/project/fortnitepy-edit/)


Asynchronous library for interacting with Fortnite and EpicGames' API and XMPP services.

**Note:** This library is still under developement so breaking changes might happen at any time.

**Some key features:**
- Full support for Friends.
- Support for XMPP events including friend and party messages + many more.
- Support for Parties.
- Support for Battle Royale stats.

# Documentation
https://fortnitepy.readthedocs.io/en/latest/

# Installing
```
# windows
py -3 -m pip install -U git+https://github.com/klldtest/fortnitepy-edit
py -3 -m pip install -U fortnitepy-edit

# linux
python3 -m pip install -U git+https://github.com/klldtest/fortnitepy-edit
python3 -m pip install -U fortnitepy-edit
```

# Basic usage
```py
import fortnitepy

from fortnitepy.ext import commands

bot = commands.Bot(
    command_prefix='!',
    auth=fortnitepy.DeviceCodeAuth()
)

@bot.event
async def event_ready():
    print(f'Bot ready as {bot.user.display_name} ({bot.user.id})')

@bot.event
async def event_friend_request(request):
    await request.accept()

@bot.command()
async def hello(ctx):
    await ctx.send('Hello!')


bot.run()
```
