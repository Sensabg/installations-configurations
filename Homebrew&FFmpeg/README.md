I also acquired some additional skills along the way, for the sake of documenting this project - I embarked on a journey to explore the creation of GIF animations.

> [!NOTE]
> Installation guide for macOS (Using Homebrew):

## Step A: Installation of FFmpeg 

1. Install Homebrew. Homebrew is a package manager for macOS that simplifies the installation of software packages. Open your terminal and run the following command to install Homebrew: 

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

2. Install FFmpeg. With Homebrew installed, you can now install FFmpeg by running the following command:

```bash
brew install ffmpeg
```

* During the installation, Homebrew may prompt you to confirm the creation of some directories and files - you can press the RETURN/ENTER key to continue with the installation. 
This is normal and is part of the installation process.

* The installation process provides instructions on how to configure your shell to include Homebrew in your PATH, which is necessary for using Homebrew commands like brew, however for your convenience, step 3 is next, explaining the process further.

3. Configure Homebrew. We already established that your shell needs Homebrew in your PATH since it is necessary for using Homebrew commands like brew so run the following commands in your terminal to add Homebrew to your PATH:

> [!IMPORTANT]
> Replace "YOURUSER" from the command below with your actual user.

```bash
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/YOURUSER/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```
> [!IMPORTANT]
> After that you may need to restart your Terminal.

4. Install FFmpeg by running:

```bash
brew install ffmpeg
```

## Step B: Create GIFs Using FFmpeg

1. Once the installation is complete, navigate back to Terminal and use the cd command to connect the directory where the videos prepared for the gif creation reside.

* if the videos are on the desktop, here is how the command should look like:

```bash
cd desktop
```
> [!IMPORTANT]
> Verify that you're in the correct directory by running the ls command, which lists the files and folders in the current directory.

```bash
ls
```

2.  Run the ffmpeg command to convert your video to a GIF. 

* Different types of commands can be used for the purpose depending on your specific needs, however, this is the exact one that I am using:

> [!IMPORTANT]
> Replace "YOURVIDEO" with the name of the video file that should be converted.
> Replace "YOURGIF.gif" with the desired name for the output gif file.

> [!NOTE]
> The parameters (fps, scale, etc.) are also adjustable.

```lua
ffmpeg -i “YOURVIDEO” -vf "fps=30,scale=480:-1" -c:v gif -b:v 3M “YOURGIF.gif"
```

<hr>

# `That's it for now! I hope you find this documentation useful. `

