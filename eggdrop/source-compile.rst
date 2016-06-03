Source Compile
--------------
This tutorial is for the brave, the stupid and the bored! If you feel like there's no
other way of getting an `eggdrop` installed on your system other than the source compile,
please read on!

Eggdrop Compile
---------------
These steps should be all that you need to compile and install the `eggdrop` all by yourself!
Configuring the sucker will be a much-much lengthier task. 

Download the eggdrop source (the latest version may vary however as of now, this does work)::

	> wget ftp://ftp.eggheads.org/pub/eggdrop/source/1.6/eggdrop1.6.21.tar.gz

Unpack the archive::

	> tar -zxf eggdrop1.6.21.tar.gz

Configure the make env::

	> ./configure

If the step above fails due to missing `tcl` proceed to the `Local Tcl` section

Setup the module being compiled::

       > make config

Execute the `Make` script::

       > make

And the final step install the compiled eggdrop into a directory you like::

       > make install DEST=~/botdir

As an additional step (as suggested by the official documentation, at this time) you can
make the botdir a bit more restrictive by chmod-ing it to 700::

     > chmod 700 ~/botdir

You should be done with installation. Configure is your next problem.


Local Tcl
---------
If you run into the problem of the `configure` script for the local `eggdrop` compilation not
finding the `tcl` shell header files. This would be *one way* to solve the problem (because lets say
the apt-get tcl tcl-dev just wont work...). You may not want to install the `tcl` directly into
your system because it'll break the paths of your favorite package system and I don't know, you
may just not need it after `eggdrop` is installed. You can follow these steps in chronological
order to get a local `/home/{user}/local` copy of `tcl` running.


Download the tcl (the latest version may vary however as of now, this does work)::

	> wget http://prdownloads.sourceforge.net/tcl/tcl8.6.4-src.tar.gz

Unpack the archive::

	> tar -zxf tcl8.6.4-src.tar.gz

Navigate into the unix directory, since it contains the `Make` scripts::

	> cd unix

Configure the make env and set the output path to your local dir::

	> ./configure --prefix=$HOME/local

Execute the `Make` script::

	> make 

Install the binaries into the `local` directory::

	> make install

You can also test Tcl working properly which should output the `tcl` version::

	> echo 'puts [info patchlevel]' | $HOME/local/bin/tclsh8.6
	> 8.6.4

Now you can `configure` the eggdrop with the library files::

	> ./configure --with-tcllib=$HOME/local/lib/libtcl8.6.so --with-tclinc=$HOME/local/include/tcl.h

If you get an error that mentions any of the libraries being linked via local install, such as this::

   error while loading shared libraries: libtcl8.6.so: cannot open shared object file: No such file or directory

Just export the `tcl` library path in the environment::

   > export LD_LIBRARY_PATH=$HOME/local/lib:${LD_LIBRARY_PATH}
