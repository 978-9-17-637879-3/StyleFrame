# StyleFrame: Run EECS280 style checks on your own computer — No CAEN needed!

## Credits:
* Apple silicon fix from https://stackoverflow.com/a/71611002
* Thanks to Nia for helping test!
* Thanks to Zalan Shah for coming up with the pre-commit hook idea!

## Requirements:
* If you don't already have docker installed and setup: ~8 gigabytes of available space.

## Installation instructions:

Step 1: Install Docker

Note: do not make a docker account, it's completely unnecessary.

For Windows, follow [this guide](https://docs.docker.com/desktop/install/windows-install/#install-docker-desktop-on-windows), then [this guide](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers#install-docker-desktop), steps 1 through 6 under "Install Docker Desktop"

For MacOS, follow [this guide](https://docs.docker.com/desktop/install/mac-install/). Be sure to download the version that matches your system (M1/M2/etc is Apple Silicon, everything else is Intel)

For Linux, follow [this guide](https://docs.docker.com/engine/install/#server), enable and start the docker service as well. Unlike MacOS and Windows, you don't need to worry about anything related to Docker Desktop, as you only have Docker engine.

Under settings in docker desktop, make sure "Start Docker Desktop when you log in" is enabled, and "Send usage statistics" + "Open Docker Dashboard at startup" are disabled

Step 2: Install StyleFrame

Download either the zip or tar.gz file from [the latest release](https://github.com/978-9-17-637879-3/StyleFrame/releases) with respect to your computer type

Extract the style_frame_files folder into your project folder

Add the contents of AddToMakefile.txt to the bottom of your Makefile

Step 3: Prepare StyleFrame base

Wherever you normally run make commands, run `make create_style_frame`

If the installation was successful, you should see some licenses printed out that you have to read

If the installation fails due to timeout or similar, run the command a few more times, if it still doesn't success, follow the instructions at "How to report issues" near the bottom of this page.

Step 4 (**OPTIONAL**): Add git pre-commit hook

If you use git and would like StyleFrame to automatically prevent you from committing when you have files that do not pass the style check, copy the file called "pre-commit" into your project folder, specifically the "hooks" folder inside the ".git" folder

Note that ".git" is hidden by default and you may need to search something along the lines of "how to show hidden files on XYZ computer"

## How to use:

When you wish to perform a style check, run `make style_frame`

## Common issues:

**ERROR [internal] load metadata for docker.io/library/style-frame-base:latest**

* Docker could not find the StyleFrame base on your computer. run `make create_style_frame` and see if the issue persists

**ERROR: failed to solve: style-frame-base:latest: failed to authorize: failed to fetch anonymous token: Get "https<nolink>://auth.docker.io/token?scope=repository%3Alibrary%2Fstyle-frame-base%3Apull&service=registry.docker.io": dial tcp: lookup auth.docker.io: i/o timeout**

* Docker could not connect to its servers. Possible solutions (perform them in this order, checking if the command works after each step):

  1. Disconnect and reconnect your internet
  2. Go to docker desktop settings -> resources -> network, then turn on manual dns configuration and use 1.1.1.1 for the DNS
  3. Quit Docker Desktop, then reopen (do not use the restart option)
  4. Restart your computer

* If the issue still persists after all of these steps, contact me via a method listed below.


## How to report issues:

Add a followup discussion to the Piazza thread, make a [GitHub issue](https://github.com/978-9-17-637879-3/StyleFrame/issues), or contact me via your umich email (my uniqname is in my Piazza name)
