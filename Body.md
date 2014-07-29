Changelog (for 1st Edition)
------
1/18/14
First revision of “Mastering Snoonet Bots”

Preamble
------
In this eBook, you will learn the basics of operating various bots available in the Snoonet network. This is also useful as a reference book for operating those bots in the future.

If this is your first time using a bot on Snoonet, we recommend trying out the exercises in a Private Message to the bot, or an empty channel, rather than using it in a busy channel, as you may cause disturbance and trigger spam protection.

Many of the bots mentioned in this book have their source code publicly available. While the author of this book has made sure that the sources for each bot are accurate, the source code may move or change, in which case links and source seen in this book may not be accurate.

Introduction
------
Welcome to Mastering Snoonet Bots!

Most of the lessons you will be using in this book have been made for use in an IRC client. If you do not have an IRC client handy, we recommend you get one set up before continuing with this book. In this book, most bots will use the prefix mentioned in each page for command detection, however other methods may also be used to detect commands, such as “Bot Name, <command>” and no prefix in PMs. See the source code of each bot for more on command prefixes. We assume each bot uses their default call prefix for the remainder of this book.

Conventions used in this Book
------
Within this book, we will use the following features to define different contexts within the text.

		Monospaced Text on a green or blue background denote commands to use in an actual IRC channel or PM.
		Red Underlined Text denotes an variable in a command that should be replaced when actually using it.
		Orange Semibold Text denotes an user, if one is used in a command.
		Blue Italic Text denotes a constant that can be used in a command, or a location on your filesystem.
		Purple Monospaced Text denotes a response from a bot.
		

Book Organization
------
The book is organized by more popular bots first, then less popular bots and their administrative tools later. Some of the lessons can only be performed by an user with the right permissions, in which case you might have to query an Operator in order to see if such restrictions apply to you.

SubBot
======
A bot that announces new Reddit posts.

SubBot allows your channel to integrate with the Reddit community, by announcing new posts from any subreddit within your channel. The announcements are in real time, and works great for Reddit communities connecting with their IRC counterparts

Source Code for SubBot can be found on Github at https://github.com/paradox460/subbot

Managing SubBot
------
After inviting SubBot into your channel, configuring SubBot is simple. To add a new channel to the list that SubBot should announce, use:
	\subreddit add <subreddit>
In the above command, the back-slash tells SubBot that this is a command to detect. The subreddit you input should just be the name, without /r/.
To remove a subreddit you added, use:
	\subreddit del <subreddit>
 Note that the subreddit you remove should be spelled exactly as it is called. This command is case-sensitive.
A list of subreddits currently being announced can be obtained with:
	\subreddit list 

After configuring SubBot, new announcements should start appearing. These announcements looks somewhat similar to this:
/r/all: <purebishop> My Test Post ( http://redd.it/2c1vhj ) [ self.all ]

Each announcement contains the subreddit it comes from, the user who posted it, the name of the post, a link to the post, and finally the type of post.
If you wish to make the bot leave the current channel, use:
	\part

Configuring SubBot
If you are hosting your own SubBot instance, you can also configure the bot’s prefix, bot name, channels to join, as well as users allowed to manage the bot. SubBot’s configuration can be found in conf/config.yml on your server’s filesystem.
Note that hosting your own SubBot instance requires a Reddit API account, as well as permission from your network to operate the bot.
Fun Fact: SubBot was written in Ruby.MemeBot
A generator for memes.
MemeBot allows you to create a “meme” within IRC. The text used in the meme is inputed as a command, and the results are returned as a link to imgur.
Source Code for MemeBot can be found on Github, at https://github.com/paradox460/memebot
Creating Memes
After inviting MemeBot into your channel, you can start generating Memes by using:
	!meme [m:MemeName] <Top Text>;<Bottom Text>
In the above command, you pick your meme, then specify the top and bottom text, separated by a colon.
After a few seconds, your meme will be returned, similar to this:
	User: http://i.imgur.com/gTvYMDq.jpg
You can also have MemeBot choose the meme for you, using:
	!meme <Top Text>;<Bottom Text>
This will return a meme using your text, but with a randomly picked background.
To list all the memes available to use for generating one, use:
	!memes
Fun Fact: MemeBot was also written in Ruby, in “a single nights bathtub coding session”.ImageBot
A bot for getting random subreddit images.
ImageBot allows you to get an image from a subreddit’s posts. This is great for looking at interesting content.
Retrieving an Image
After inviting ImageBot into your channel, you can get an image from a subreddit by using:
	!image <subreddit>

Fun Fact: ImageBot is based on the Cinch framework.
