Configure
---------


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


