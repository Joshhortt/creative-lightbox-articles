# How can we build DApps using the Internet computer?

This is a step-by-step tutorial for Windows users to install, set up, and deploy a "Hello" DApp to the Internet Computer (IC) in 1 hour or less. Deployment of the DApp only requires basic knowledge of using a terminal. Before starting, take a look at a version of [this DApp running on-chain:](https://6lqbm-ryaaa-aaaai-qibsa-cai.ic0.app/)

### 1\. Make sure that you got the correct system requirements

So if you go into the start menu on Windows and search for system information, then you can see what Operating System version you're running.

So at a minimum, you should be running **Windows 10, version 2004 or above**, and you can tell that's the correct version by looking at this version and seeing that it's 19041 or above and I've got 19045 here, so that's perfect.

And also, if you're running **Windows 11 or above**, that's fine.

#### 2\. Make sure that you're running 64-bit Windows

Under system type, you should see **"x64."** Unfortunately, it's not going to work very well with 32-bit.

So these are the two main **requirements**.

Next, you're going to go and search for **PowerShell**

#### 3\. Make sure that you open Powershell as an Administrator

![open powershell as administrator](https://cdn.hashnode.com/res/hashnode/image/upload/v1672235716216/88813190-cd26-497d-af00-d8ad15e097ad.png?auto=compress align="left")

Start by writing the following line of code into PowerShell:

```bash
$ wsl --install
```

![wsl install powershell](https://cdn.hashnode.com/res/hashnode/image/upload/v1672235774880/1e3f0b68-4943-46d7-9802-9e326627dfd8.png?auto=compress align="left")

It's going to install something called the Windows sub-machine for Linux.

It's going to give us a **virtual Linux environment** to work with, allowing us to run bash commands, which are required when you're working with the Dfinity internet computer.

So this is going to take a little while to run, but once it's done, it'll tell you the request operation is successful, but you have to restart your machine for it to take effect.

#### 4\. Once that’s done, you’ll need to restart your computer

And once it has restarted and been launched again, it should automatically bring up the pane below where you need to set up a username and password for working with Ubuntu.

Upon restart, you will be prompted to **set up an ubuntu username and password** and then you will have successfully installed WSL.

**Note:** *Keep a note of both of these pieces of information, you’ll need it later on. When you type your password it will not show up, just make sure you know what you’re typing!*

#### 5\. Enter those pieces of information (username & password)

Be sure you know what you're typing, and maybe keep it simple as well because you're going to be using this password, very shortly when you're installing other components.

![password & username](https://cdn.hashnode.com/res/hashnode/image/upload/v1672236135826/8f07514f-670c-4991-b3ca-77b6fa2b1528.png?auto=compress align="left")

Now, once that is complete, go ahead and open up Windows PowerShell as the administrator again.

#### 6\. To confirm that everything worked, type the following command into PowerShell

```bash
$ wsl --list --verbose
```

And this just checks that wsl was correctly installed.

As long as you see Ubuntu version two listed there, you are good to go.

#### 7\. You should see in Powershell an output like this

![powershell output](https://cdn.hashnode.com/res/hashnode/image/upload/v1672236752126/126a51ec-554a-43f2-a98b-2e3e88c3dc19.png?auto=compress align="left")

**You're ready to go to the next step, which is to install Visual Studio code if you haven’t done so.**

#### 8\. Download and install the latest version of VSCode

and follow the instructions below

* Download the [Visual Studio Code installer](https://go.microsoft.com/fwlink/?LinkID=534107) for Windows.
    
* Once it is downloaded, run the installer (VSCodeUserSetup-{version}.exe). This will only take a minute.
    
* By default, VS Code is installed under C:\\Users\\{Username}\\AppData\\Local\\Programs\\Microsoft VS Code.
    

Alternatively, you can also download a [Zip archive](https://code.visualstudio.com/docs/?dv=winzip), extract it and run Code from there.

**Tip:** *Setup will add Visual Studio Code to your %PATH%, so from the console, you can type* ***'code .'*** *to open VS Code in that folder. You will need to restart your console after the installation for the change to the %PATH% environmental variable to take effect.*

Now, once the installation has been completed, it will automatically launch.

And what you're going to do is you're going to install some required extensions to VSCode IDE.

Now leave VSCode IDE open, then…

#### 9\. Install the Motoko language extension in VSCode

So, head over to the installation guide and copy the first link for the [Motoko extension](https://marketplace.visualstudio.com/items?itemName=dfinity-foundation.vscode-motoko) and paste it into the browser. Make sure it’s from the **Dfinity** team.

![motoko extension](https://cdn.hashnode.com/res/hashnode/image/upload/v1672236941986/746123df-d273-4287-9082-d2d6ed767987.png?auto=compress align="left")

And if you click on "install" in your browser, then it should be able to bring up Visual Studio Code and allow you to open that link inside VSCode.

![motoko installed](https://cdn.hashnode.com/res/hashnode/image/upload/v1672236997970/a8221acc-10e1-4823-a7d9-e71e37505b4c.png?auto=compress align="left")

There are quite a few extensions called Motoko, but you want the one that's from the Dfinity Foundation.

#### 10\. Install the Remote WSL extension

And then you're going to install your [remote wsl](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl), which is going to allow you to use the terminal inside.

![wsl extension](https://cdn.hashnode.com/res/hashnode/image/upload/v1672237046001/b8726b5e-b568-4737-9090-33ff244c4e8c.png?auto=compress align="left")

VSCode and tap into that wsl that you installed earlier on.

![wsl installed](https://cdn.hashnode.com/res/hashnode/image/upload/v1672237079359/54e8a717-3e11-4346-9b29-7c6c942e03bb.png?auto=compress align="left")

**Now, finally, you're ready to go ahead and install Node into wsl.**

So, this means that even if you have installed Node before on your Windows computer, you have to do this again just so that you can work with WSL, Node, Dfinity, and everything else.

![node](https://cdn.hashnode.com/res/hashnode/image/upload/v1672237116113/1ce8b157-211c-41bc-bca3-23576915090d.png?auto=compress align="left")

#### 11\. Search and open up Ubuntu

Homebrew will make it easier for us to install other tools, such as Node. You might already have Node installed on your Windows system, but because we’re working with WSL, you’ll need to install it on your Linux system too.

#### 12\. Install Homebrew

![install homebrew](https://cdn.hashnode.com/res/hashnode/image/upload/v1672237186643/30d37d56-a110-4bff-a973-a9585e875e82.png?auto=compress align="left")

So either goes over to the homebrew link that's in the installation guide or simply just copy that command and open up Ubuntu from the start menu and paste that command in and run it.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**Alternatively copy it from the homebrew website:** [**https://brew.sh/**](https://brew.sh/)

#### 13\. Enter the password for the user that you set before in step 5

During the installation process, it's going to ask you for the password that you set just a moment ago when you set up Ubuntu, and you just need to type that in right now. When they ask you to confirm, go ahead and hit ENTER.

Now once it's done installing homebrew, there are a few steps that you have to complete.

#### 14\. The installer will tell you how to add brew to the PATH

Copy these three commands and run them one by one in Ubuntu.

```bash
$ echo '# Set PATH, MANPATH, etc., for Homebrew.' >> /home/josec/.profile
```

```bash
$ echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> /home/josec/.profile
```

```bash
$ eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

This is going to make homebrew available to use in the path. It doesn't matter if you don't understand what that means. It's just a little bit of manual setup that's required.

**Now underneath the last three commands, you only have to install another four commands before installing DFX.**

#### 15\. Install Homebrew’s dependencies if you have sudo access

And finally add that part that's underneath the install homebrew dependencies, enter your password and type 'Y' when they ask you to and let it go through the full installation process.

```javascript
$ sudo apt-get install build-essential
```

Now once you see that dollar sign again, that means it's all done and you can now...

#### 16\. Check and make sure by typing the following command

```javascript
$ brew --version
```

And if you see homebrew followed by some sort of version number, like:

```javascript
$ brew --version
Homebrew 3.6.16
Homebrew/homebrew-core (git revision ff690e6841d, last commit 2022-12-27)
```

then that means everything was successful.

Now finally, you're going to use Homebrew to install Node version 16.

#### 17\. Install node using homebrew with the following command

```javascript
$ brew install node@16
```

This is the latest stable version and this is the version that will work with the Internet computer very well.

So you must follow this command.

Now, if you get this error that I've got, `node 16 is keg-only`, which means it was not symlinked, this is because you have another node version installed on your computer and all you have to do is simply type `brew link node@16` to link to this version that we just installed.

```javascript
$ brew link node@16
```

#### 18\. Once it’s done check that it worked with

```javascript
$ node --version
```

And as long as you get a version that starts with 16, then you are ready to roll.

## Install DFX

Finally, you are ready to install DFX. So go ahead, and from your Windows start menu:

#### 19\. Open up Ubuntu

#### 20\. Copy/paste the following command into your terminal and hit enter to install DFX

```bash
$ DFX_VERSION=0.9.3 sh -ci "$(curl -fsSL https://sdk.dfinity.org/install.sh)"
```

Now it's going to take a little while to fetch DFX which is the package that's going to allow us to work with the Internet Computer locally. Once it is installed, then it's going to tell you where it was installed and you have to manually set up the path to point to that location.

```bash
$ DFX_VERSION=0.9.3 "(install.sh)"
info: installed /home/josec/bin/dfx
```

e.g. in my case, it tells me that it has been installed in **/home/josec/bin/dfx**

So in the installation guide, I've got this stub for you which I want you to paste into notepad and replace the part which says 'replace with your installation path' with the installation path you got from the dfx install.

#### 21\. Copy the installation path you got from the last step

and replace &lt;REPLACE WITH YOUR INSTALLATION PATH&gt; from the command below (You can use Notepad for this)

```bash
$ export PATH=$PATH:/home/josec/bin/dfx
```

E.g. in my case, it would be export PATH=$PATH:/home/josec/bin/dfx

#### 22\. Paste the formatted command from the previous step and hit enter

So copy that, paste that in there, and make sure there's no space between the colon and the first forward slash.

#### 23\. Check it has been added by running the following command

```bash
$ echo "${PATH//:/$'\n'}"
```

Copy that entire command, paste it back into Ubuntu, and hit enter to run that command.

And now if you copy that line where it says echo and then a bunch of symbols, you should be able to see that your DFX location was added to your path as I've got here.

#### 24\. Check that DFX has been successfully installed with the following command

```bash
$ dfx --version
```

Now, finally, after you run `dfx --version` and you should see `dfx 0.9.3.`

And if you do, then that means DFX was successfully installed and you're ready to finally get started by creating your first Internet Computer application.

**Note:** In This short tutorial I'll be using **dfx 9.0.3** and if you have been following along keep that version running, **even if it prompts you to upgrade DFX, don’t UPGRADE!**

## Test Everything Creating and Deploying your First DApp

### Create the Default Hello DApp

#### 1\. Open up VSCode and click on that little green icon

Open up VSCode and click on that little green icon to the bottom left and select the **new wsl window**.

Now, once you've done that, you can close down the previous window if you want, but make sure that the window that you're working with says WSL: Ubuntu.

And if you hover over it, it should say running in Ubuntu.

![running on ubuntu](https://cdn.hashnode.com/res/hashnode/image/upload/v1672244108656/Nb3tZVrSS.png?auto=compress align="left")

#### 2\. Open Ubuntu and create a directory called ic-projects

Now go ahead and open up Ubuntu from the start menu again and you're going to create a directory called `ic-projects` with the make directory command:

```bash
$ mkdir ic-projects
```

So copy/paste this command or you can type it out.

But you're creating this folder called `ic-projects` inside our main user folder, and then you're going to `cd` or change the directory into that newly created folder.

#### 3\. Change the directory into that folder

Change the directory into that folder by using the following command:

```bash
$ cd ic-projects
```

#### 4\. Create your first Internet Computer Dapp

Inside this `ic-projects` folder, you’re going to create our first Internet Computer DApp. Go ahead and type the following command:

```bash
$ dfx new hello
```

And this is going to build you a sample Internet Computer application called **Hello**.

And leave it in the background running.

And once it's built, you'll see the Dfinity logo show up and you can see where you’re folders and files are by using the command `explorer.exe .` and you can see your hello folder with all of the template files that DFX created for you.

```bash
~/ic-projects$
```

#### 5\. Confirm your project files and folders

You can see this new project and folders by running the following command:

```bash
~/ic-projects$ explorer.exe .
```

![Hello Logo](https://cdn.hashnode.com/res/hashnode/image/upload/v1672768599585/o76PoKnO3.png?auto=compress align="left")

#### 6\. Open up VSCode and click on that little green icon

Open VSCode again and click on the green icon as you did in step 1.

And you can now go back to VSCode, and select the open folder, select the ic-projects/hello.

And it should now open up our project in VSCode.

Now if you take a look inside the source folder, you'll see all the source files for this project.

And you've got your [`main.mo`](http://main.mo) which is your Motoko file.

Just in case, it doesn't have any syntax highlighting, which is what our Motoko extension is supposed to do, head over to the extensions tab, you can see this extension is currently disabled if that's the case.

And I want you to click on that button where it says to install in WSL: Ubuntu so that you can make it available in your WSL remote.

![activate motoko extension](https://cdn.hashnode.com/res/hashnode/image/upload/v1672768363436/Ow6HPWFoD.PNG?auto=compress align="left")

Now finally you can head back to your [`main.mo`](http://main.mo) and you should see all the syntax highlighting working just fine.

### Deploy the DApp

Now there are also some HTML files and JS files, but you're now ready to deploy.

So go into the terminal menu and then open up a new terminal.

And here I want you to write to start `dfx start` to start the local Internet computer.

```javascript
$ dfx start
```

And now once you see this listing on something, then I want you to split out a new terminal window by clicking on the `+` button showing in the image below, and then type in `dfx deploy` to deploy this hello project onto that local DFX that you just started.

![add new terminal](https://cdn.hashnode.com/res/hashnode/image/upload/v1672763604133/WMWLVkuGS.png?auto=compress align="left")

```javascript
$ dfx deploy
```

Once it's done and you see a dollar sign again, you're going to type `npm start` to start up your server.

```javascript
$ npm start
```

And if you scroll up, you see, it tells you where the project is running.

So go ahead and copy that URL and paste it into your browser or Open a browser and navigate to [**http://localhost:8080/**](http://localhost:8080/).

**Note that:** You might see a different server URL showing in your terminal, it can be [http://localhost:3000/](http://localhost:3000/) or [http://localhost:5000/](http://localhost:5000/) or some other local server host.

And once it loads up, you'll see your starter project, type in your name, and click on `Click Me!` button and you'll see the greeting show up.

![Hello, Click Me!](https://cdn.hashnode.com/res/hashnode/image/upload/v1672765162014/UEOWl1ypp.png?auto=compress align="left")

And that means you have successfully installed and set up everything that's required to start developing on the Internet computer.

### Stop the local canister execution environment

After testing the application in the browser, you can stop the local canister execution environment so that it does not continue running in the background. We will not need it running to deploy on-chain.

#### To stop the local deployment:

* In terminal A, press Control-C to interrupt the local network process.
    
* In terminal B, press Control-C to interrupt the development server process.
    
* Stop the local canister execution environment running on your local computer:
    

```bash
$ dfx stop
```

### Troubleshooting

#### Node.js is not properly installed

If your DApp does not show in the browser, it is possible that Node.js is not correctly installed. Confirm it is installed by running:

```javascript
$ node --version
```

#### Prior installations of DFX

If you have previously created IC DApps before February 2022, you may need to do a clean install. You can delete the SDK and associated profiles and re-install it. Follow the instructions here: [Install, upgrade, or remove the software](https://internetcomputer.org/docs/current/developer-docs/build/install-upgrade-remove).

### Upgrading to the latest version

If a new version of the SDK is available for download after your initial installation, you should install the updated version at your earliest convenience to get the latest fixes and enhancements as soon as possible. You can use the `dfx upgrade` command to compare the version you have currently installed against the latest version available for download. If a newer version of dfx is available, the `dfx upgrade` command automatically downloads and installs the latest version.

```bash
$ dfx upgrade
```

Note that you don't need to uninstall the software before installing the new version. However, if you want to perform a clean installation rather than an upgrade, you can first uninstall the software as described in [Removing the software](https://internetcomputer.org/docs/current/developer-docs/build/install-upgrade-remove#removing-the-software), then re-run the download and installation command.

For information about the features and fixes in the latest release, see the [Developer Release notes](https://internetcomputer.org/docs/current/developer-docs/updates/release-notes/sdk-release-notes).

## What are some developer resources for building on the Internet Computer?

I want also to share an extensive list of Dfinity developer documentation, tools, and other [developer resources](https://support.dfinity.org/hc/en-us/sections/8730538838804-Developers) for creating projects on the Internet Computer.

### General Internet Computer Tutorials

* [Coding with Kyle Video Tutorial Series:](https://www.youtube.com/watch?v=M2XnywvwxFM&list=PLuhDt1vhGcrfQGLWqhUo9-DFD5JaHqCh1&ab_channel=DFINITY) Learn how to build an IC Avatar DApp with DFINITY Developer Kyle Peacock.
    
* [The Complete 2022 Web Development Bootcamp](https://www.udemy.com/course/the-complete-web-development-bootcamp/): It is a Full Web developer Bootcamp of 65 hours in total. Section 34 onwards is a 10+ hour course about building on the IC.
    
* [Series on low-level interaction with the Internet Computer by Ben Lynn](https://fxa77-fiaaa-aaaae-aaana-cai.raw.ic0.app/organic/)
    

## Wrap-up

Congratulations! You learned how to Set up your computer to be able to develop decentralized applications using the Internet Computer and you also have built your first "Hello" DApp fully on-chain (both backend and frontend) hopefully within 1 hour.

## Tutorial takeaways:

* DApps can be composed of multiple canisters.
    
* DApps can be deployed locally and on-chain.
    
* The "Hello" DApp consists of backend code written in Motoko, a programming language specifically designed for interacting with the Internet Computer, and a simple webpack-based frontend.
    

## Where to Get Help and Support for Development on the IC?

As you go through the tutorials and start coming up with ideas for personal projects, it might be a good idea to be aware of all the places where you can get help for working with the Internet Computer, the links below are worth bookmarking!

* [Official Developer Docs](https://internetcomputer.org/docs/current/developer-docs/quickstart/hello10mins)
    
* [Command-line Reference](https://internetcomputer.org/docs/current/references/cli-reference/)
    
* [Official Dfinity Forum](https://forum.dfinity.org/)
    
* [Official Dfinity Developer Discord](https://discord.com/invite/cA7y6ezyE2)
    

## Want to learn more from my articles?

If you are looking for more information about the Internet Computer, check out the following article [What is the Internet Computer?](https://creativelightbox.net/what-is-the-internet-computer) posted on Dec 29, 2022.

**Thanks for the read! Now go build something awesome!**