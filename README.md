# StyleFrame: Run EECS280 style checks on your own computer — No CAEN needed!

## Requirements:
* A few gigabytes of available space

## Installation instructions:

Step 1: Install Docker

Note: do not make a docker account, it's completely unnecessary.

For Windows, follow [this guide](https://docs.docker.com/desktop/install/windows-install/#install-docker-desktop-on-windows), then [this guide](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers#install-docker-desktop), steps 1 through 6 under "Install Docker Desktop"

For MacOS, follow [this guide](https://docs.docker.com/desktop/install/mac-install/). Be sure to download the version that matches your system (Intel vs Apple chip)

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

## How to use:

When you wish to perform a style check, run `make style_frame`

## How to report issues:

Add a followup discussion to the Piazza thread, make a [GitHub issue](https://github.com/978-9-17-637879-3/StyleFrame/issues), or contact me via your umich email (my unique name is in my Piazza name)
