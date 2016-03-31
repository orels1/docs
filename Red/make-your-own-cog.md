#Creating custom cogs
The purpose of this tutorial is to help you create your first custom cog for Red Discord bot.

**Contents**  
[Boilerplate](#boilerplate)  
[Mentioning users](#mentioning-users)  
[Getting info from webpages](#getting-info-from-webpages)

###Boilerplate
First of all you need a nice and clean boilerplate to work with.
P.S. `[p]` is your prefix for the bot.

 1. Create a file `mycog.py` and open it with any text editor, I can recommend [Sublime Text 3](https://www.sublimetext.com/)
 2. Copy and paste the following code

```python
import discord
from discord.ext import commands
import random

class Mycog:
    """My custom cog that does stuff!"""

    def __init__(self, bot):
        self.bot = bot

    @commands.command()
    async def mycom(self):
        """This does stuff!"""

        #Your code will go here
        await self.bot.say("I can do stuff!")

def setup(bot):
    bot.add_cog(Mycog(bot))

```

 3. Now you'll have a basic module that replies "I can do stuff" when you call `[p]mycom`
 4. Load your new module with `[p]load mycog`
 5. Test your command with `[p]mycom`
 6. Bot should respond with `I can do stuff!`

Now you have a basic command interface! Let's make it more interesting, shall we?

###Mentioning users
Sometimes I want to punch something, or someone, but I'm weak, and I need some help. That's why we'll make a bot puch someone, instead of ourselves.

 1. In your code change `async def mycom(self):` to `async def punch(self, user : discord.Member):` so now it will react to `[p]punch` and accept a user mention as a parameter
 
The command's code should now look something like this

```python
...

@commands.command()
async def punch(self, user : discord.Member):
    """I will puch anyone! >.<"""

    #Your code will go here
    await self.bot.say("I can do stuff!")

...
```

 2. But if you reload the cog with `[p]reload mycog` it will still say `I can do stuff` which is not what we want
 3. Change your response to :
```python
await self.bot.say("ONE PUNCH! And " + user.mention + " is out! ლ(ಠ益ಠლ)")
```

*You can use any message, just remember to `+ user.mention` somewhere in there for cog to target your prey!*

 4. Reload the cog with `[p]reload mycog`

Now you can punch other people without getting your hands dirty, awesome! You can try to play around with it as you like!

###Getting info from webpages

