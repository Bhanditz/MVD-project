#Detailed install instructions

Make sure you have `build-essentials` if you are on Linux, and the XCode Developer Tools and XCode Command Line Tools if you are in a Mac.

Install git from your package manager, if you do not already have it.

Install the JDK8 from your package manager, or from Oracle.

Install Mirah - this is slightly involved.

Get the BIMserver jar files from https://github.com/opensourceBIM/BIMserver/releases/tag/1.4.0-FINAL-2015-11-04

Extract the BIMserver jar files into a location they can stay in; you will need these on your CLASSPATH to build BIMserver-query-plugin-shell and to build any MVDs.

Clone the MVD-project repo into your third party code directory, including all submodules, using `git clone --recurse-submodules https://github.com/flaviusb/MVD-project.git`.

##Installing Mirah

First install rvm from rvm.io if you do not have it.

Then `rvm install jruby` and `rvm --default use jruby` to install jruby and make it your default ruby.

Then, cd into the directory you use for building third party projects, and run:

```
$ git clone http://github.com/mirah/mirah.git
$ cd mirah
$ bundle install
$ rake gem
$ gem install pkg/mirah-*.gem
$ rake dist/mirahc.jar
```
