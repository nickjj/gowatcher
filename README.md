# <a href="#gowatcher" name="gowatcher">gowatcher</a>

A bash script to automatically reload a go program when anything changes in the monitored directory. It uses inotify.

## Installation

Do you have inotify-tools already installed? Great, then skip step 1.

### Step 1: (installing the dependency)
    $ sudo apt-get install inotify-tools

Replace apt-get install with whatever package manager you use.

### Step 2: (downloading and preparing the script)

    $ curl http://raw.github.com/nickjj/gowatcher/gowatcher > gowatcher && chmod 700 gowatcher

That just grabs the latest copy from this repo and changes the privileges of the file so that it is executable.

At this point you'll want to move *gowatcher* into a directory that is on your system path so that you can run it from any directory.

You're also done unless you do not know how to do that, in which case continue onto step 3.

### Step 3: (setting a directory on your system path)

If you do not have any directories on your system path it is pretty common to add a **bin** folder in your home directory. You can do that if you like and then at the bottom of your *.bashrc* file you can add:

    export PATH=/home/username/bin

If you have one path there already you can separate it by a colon. Example:

    export PATH=/home/username/bin:/some/other/path

Where *username* is your actual username, then save the file and reload your shell by doing:

    $ source ~/.bashrc

## Usage

    $ cd path/to/the/dir/you/want/to/watch
    $ gowatcher file-to-start.go

In other words, goto the directory you want to monitor and input the path to the go file containing your main() function.