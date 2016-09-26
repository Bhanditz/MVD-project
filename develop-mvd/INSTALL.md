#Detailed install instructions

Make sure you have the `build-essentials` metapackage (or your distribution's equivalent) if you are on Linux, and the XCode Developer Tools and XCode Command Line Tools if you are in a Mac.

If you are on a Mac and do not have a package manager, consider installing [https://brew.sh](homebrew).

Install git and GNU make from your package manager, if you do not already have them.

Install JDK8 (or later) from your package manager, or from Oracle.

Install Mirah - this is slightly involved.

Get the BIMserver jar files from https://github.com/opensourceBIM/BIMserver/releases/tag/1.4.0-FINAL-2015-11-04
The jar files you need are in the lib subdirectory of the `bimserver-1.4.0-FINAL-2015-11-04.jar` file.

Extract the BIMserver jar files into a location they can stay in; you will need these on your CLASSPATH to build BIMserver-query-plugin-shell and to build any MVDs - any Makefiles or buildscripts will usually need a variable set to get this location.

Clone the MVD-project repo into your third party code directory, including all submodules, using `git clone --recurse-submodules https://github.com/flaviusb/MVD-project.git`.

##Installing Mirah

First install rvm from [https://rvm.io](rvm.io) if you do not have it.

You can skip the installation of gpg2 if you trust the distribution point of rvm.

Then install Apache Ant. You can get it from your package manager, or download it from [https://ant.apache.org](ant.apache.org).

Then `rvm install jruby` and `rvm --default use jruby` to install jruby and make it your default ruby.

Then, cd into the directory you use for building third party projects, and run:

```
$ git clone http://github.com/mirah/mirah.git
$ cd mirah
$ gem install rake
$ gem install bundle
$ bundle install
$ rake gem
$ gem install pkg/mirah-*.gem
$ rake dist/mirahc.jar
```

If you have problems with Mirah, commit 63a6b628c2072031e8228570cb051be59e926ef8 works. You can change to this commit by running 
`$ git checkout 63a6b628c2072031e8228570cb051be59e926ef8` on a fresh clone.
