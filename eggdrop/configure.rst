Configure
---------
The task of configuring your bot is a lengthy task as the eggdrop.conf is over 1100 lines
long and defines quite a bit of settings that all have effect on your bot. What you will find below
is a bare minimum set of settings I found I needed to change to be happy with my bot running as a process
on my machines.

Before you begin you must understand that the conf file contains a few (more like just a couple) of
termination points (a die() command) that will force you to remove/uncomment these line in the
config you'll generate. The owner of the project felt that it is IMPORTANT that you find and remove
these by yourself. This perhaps is a clue as to the dangers of just running a default config. 

The list of settings below is not exclusive neither are they authoritarian. These are merely
suggestions that you should find useful before forming a strong opinion on what should be set
or unset.


Settings
--------
Defines the settings that found are important to change in default config.


Set the username under which the `eggdrop` will run as::

	set username "{username}"

Set the network this bot connects to::

	set network "EFNET"

Log private message and ctcps by setting this line::

	logfile mco * "logs/{bot-name}.log"

logging joins/parts/kick/message from as many channels as you like by 
adding the following line(s)::

	logfile jpk #{channel} "logs/{channel}.log"

Set the user file::

	set userfile "{bot-name}.user"

Set the listen port::

	listen {random number between 49152 - 65535}

Set the owner irc nick. This is important as you'll may set the owner/master password
via IRC and the bot will only accept it from this nick::

	set owner "{your irc nick}"

Disable execution of tcl and set commands::

	unbind dcc n tcl *dcc:tcl
	unbind dcc n set *dcc:set

Set the name of the dynamic channel settings::

	set chanfile "{bot-name}.chan"

Set the channels the bot should join::

	channel add #{your channel}

Set the bot irc nick::

	set nick "{bot irc nick}"

Set the bot alt irc nick::

    set altnick "{alt bot irc nick}"

Set the bot realname, usually it's something very clever::

    set realname "hydrogen turns to helium when i shine"

Set the bot servers, this is the list of irc networks the bot will
try to connect to::

    set servers {
    		efnet.multiplay.co.uk
		efnet.port80.se
		efnet.portlane.se
		irc.du.se
		irc.efnet.fr
		irc.efnet.pl
		irc.homelien.no
		irc.inet.tele.dk
		irc.inter.net.il
		irc.swepipe.se
		irc.underworld.no
		irc.choopa.net
		irc.colosolutions.net
		irc.mzima.net
		irc.paraphysics.net
		irc.Prison.NET
		irc.servercentral.net
    		irc.shaw.ca
		irc.umich.edu
	}

Enable the bot to try to regain its irc nick if it's ever unavailable::

	set keep-nick 1

Make sure this is set to 0, you don't want people to register with the
bot as they wish::

     set learn-users 0

Change the default default msg reply from hello to something original::

     unbind msg - hello *msg:hello
     bind msg - hola *msg:hello

Change the default commands that are used to identify a host or add a new host
with something random and may be silly::

     unbind msg - ident *msg:ident
     unbind msg - addhost *msg:addhost
     bind msg - monkey *msg:ident
     bind msg - jump *msg:addhost

Set the name of the notes file::

    set notefile "{bot-name}.notes"


Recommended security feature::

    set protect-telnet 1

Require +p flag for all users to join the party line::

    set require-p 1

Prevent the bot from spilling info about itself::

    set stealth-telnets 0
