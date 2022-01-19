OrangePi Repo Manifests for the Yocto Project Build System
=====================

Getting Started
---------------
**1.  Install Repo.**

Download the Repo script:
To simplify installation we provide a repo manifest which manages the different
git repositories and the used versions.
(more on repo: https://code.google.com/p/git-repo/ )

Install the repo bootstrap binary:

  mkdir ~/bin
  PATH=~/bin:$PATH
  curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
  chmod a+x ~/bin/repo

If it is correctly installed, you should see a Usage message when invoked
with the help flag.

    $ repo --help

**2.  Initialize a Repo client.**

Create an empty directory to hold your working files:

    $ OPI_SOURCES=/path to orangepi sources
    $ mkdir -p $OPI_SOURCES
    $ cd $OPI_SOURCES

Tell Repo where to find the manifest:

    $ repo init -u git://github.com/fullstackfpga/orangepi-manifests.git

To test out a known stable yocto version (example: orange pi zero dunfell), type:

    $ repo init -u git://github.com/fullstackfpga/orangepi-manifests.git -m orangepi-zero/default.xml -b dunfell
    $ repo sync

To get back to the latest master branch, type:

    $ repo init -u git://github.com/fullstackfpga/orangepi-manifests.git -m orangepi-zero/default.xml -b master
    $ repo sync

To learn more about repo, look at http://source.android.com/source/version-control.html
***

**3.  Fetch all the repositories:**

    $ repo sync

Now go turn on the coffee machine as this may take 20 minutes depending on your
connection.

Staying Up to Date
------------------
To pick up the latest changes for all source repositories, run:

    $ repo sync

Customize
---------
Sooner or later, you'll want to customize the Repo manifest to point at
different repositories and branches or pull in additional meta-layers.

Clone this repository (or fork it on gitenterprise):

    $ git clone git://github.com/fullstackfpga/orangepi-manifests.git

Make your changes (and contribute them back if they are generally useful), and
then re-initialize your repo client

    $ repo init -u <file:///path_to_your_git_repository.git> -m board_type/default.xml -b branch 
