#Setting env variables
I collected the ways to add environmental variables for three main platforms.

##Windows
1. Launch a command prompt with admin rights. To do that, press windows key on your keyboard, and type "cmd", rightclick on "Command Prompt" and choose "Run as administrator".
2. Type `SETX <NAME OF A VARIABLE> <VALUE OF A VARIABLE>`. For example:
```
SETX DOTA2_API_KEY 8213dsfs2sc3214ac32
```
That's it! You will need to open a new command propmt to get the update list of variables

##OSX
1. Open a terminal by clicking on a spotlight icon in your top right corner and typing "Terminal".
2. Type `nano ~/.bash_profile`, it will open up an editor
3. On a new line, add a variable like this `export <NAME OF A VARIABLE>=<VALUE OF A VARIABLE>`. For example:
```
export TWITTER_CONSUMER_KEY=HOVSNd23dahsdsvs853vsd
```
That's it! You will need to open a new terminal window to get the updated list of variables

##Linux (Ubuntu)
1. In your terminal run `sudo nano /etc/environment`
2. Add your variable like this `<NAME OF A VARIABLE>=<VALUE OF A VARIABLE>`. For example:
```
DISCORD_API_EMAIL=test@example.com
```
That's it! You will need to open a new terminal window to get the updated list of variables

Hope that helps =)
