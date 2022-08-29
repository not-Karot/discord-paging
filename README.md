# Pycord Paginator
**Pycord Paginator** is a library to paginate your messages or embeds when using [discord.py](https://discordpy.readthedocs.io/en/stable/index.html).

⚠ This library is a fork of https://github.com/Tommodev-06/pycord-paging, made for Pycord.

To install the library, open your terminal and run this command:
```
pip install git+https://github.com/not-Karot/discord-paging
```

Example with reactions:
```py
from discord import Embed
from discord.ext import commands
from paginator import Paginator, Page

bot = commands.Bot(command_prefix="!")
paginator = Paginator(bot)

@bot.event
async def on_ready():
    print("Bot online")

@bot.command()
async def paginator(ctx):
    pages = [
        Page(embed=Embed(title="Page #1", description="Testing")),
        Page(embed=Embed(title="Page #2", description="Still testing")),
        Page(embed=Embed(title="Page #3", description="Guess... testing"))
    ]

    await paginator.send(ctx.channel, pages, type=1, author=ctx.author, disable_on_timeout=False)

bot.run("...")
```

Example with buttons:
```py
from discord import Embed
from discord.ext import commands
from paginator import Paginator, Page

bot = commands.Bot(command_prefix="!")
paginator = Paginator(bot)

@bot.event
async def on_ready():
    print("Bot online")

@bot.command()
async def paginator(ctx):
    pages = [
        Page(embed=Embed(title="Page #1", description="Testing")),
        Page(embed=Embed(title="Page #2", description="Still testing")),
        Page(embed=Embed(title="Page #3", description="Guess... testing"))
    ]

    await paginator.send(ctx.channel, pages, type=2, author=ctx.author, disable_on_timeout=False)

bot.run("...")
```

Docs will be published soon... 👀
