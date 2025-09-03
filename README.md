# mcserver-termux
A simple and detailed guide to run a Minecraft Java server on your non-rooted Android phone.

## Requirements

- [Termux](https://f-droid.org/packages/com.termux/) - **Do not** install the Google Play version, it is severely outdated.

- [Material Files](https://play.google.com/store/apps/details?id=me.zhanghai.android.files) - Needed in order to manage your server easier without `cp`, `ls` and `mv` commands.

- Android phone with <ins>**Android 11 and up**</ins> installed and *at least* <ins>**4GB of RAM**</ins> (*recommended for a stable small server experience*).

- **1.5GB** of free storage in your device.

## Basic installation

Open Termux and run the following command:
```
termux-setup-storage
```
> Your phone will prompt a menu asking for all files permissions for Termux. Select Termux and exit the menu. That's needed in order to manage your server files later.

Now update Termux's packages with the following command:
```
pkg update && pkg upgrade -y
```
> This command will check all available mirrors, all upgradeable packages and then automatically install them. Some packages will require you to select certain options, in this case, always select Y.

Now you will need to install **proot-distro**, a utility that lets you easily install any ([*compatible*](https://github.com/termux/proot-distro?tab=readme-ov-file#bundled-distributions)) Linux distro on Termux, and **openjdk-21**, which is the full Java 21 package that lets you create and run your Minecraft server.

>[!NOTE]
>JDK 21 is only needed for 1.20.5+ servers. If you wanna run an older version of Minecraft Java, check [this link](https://docs.mcserversoft.com/advanced/java-version) to check which version is suitable for you.

But well, here's the command.
```
pkg install proot-distro openjdk-21
```

Now, you will need to **install a distro** directly from proot-distro. I will be installing Debian, but _**Ubuntu works in the exact same way**_.
```
proot-distro install debian
```
Once it's finished, process in which should take around a couple seconds, you can log-in into your distro with `proot-distro login <distro-name>`.

You will need to do the same update process again with Debian, now with the following command:
```
apt update && apt upgrade -y
```
> Normally, it will not have any package to install, as it is in the latest version available. That's normal.

You will also need to install `nano` for text editing and `wget` to transfer files directly from the internet.
```
apt install nano wget
```

For a basic installation, there's no need to install any more packages. In order to **install your server**, you will **need a proper folder** for it.

For this, use the command `mkdir` alongside the name of the folder you wanna create. In my case, it will be named `server`.
```
mkdir server/
```

Now, select your newest server directory with `cd` and the name of your folder.
```
cd server
```

In order to **create your server**, you need a **specific .jar server file** from the internet. It can be any game server that you want, but i will use **PaperMC**.

Hold the download button from the website, copy the link of the file, and download it into your server folder with `wget`.
```
wget https://fill-data.papermc.io/v1/objects/1798de5d5f81f6aa4deedf8372326e17796a2566d46a55486bfbc9fbc47c7394/paper-1.21.8-56.jar
```
>[!NOTE]
> This is just a command example. This guide will eventually be outdated over time, you don't need to copy this exact file, just grab the one you want.

Once it's downloaded, just for simplicity, i'd recommend **cleaning up the file's name** with a 'mv' command. In this case, i will rename it to just `paper.jar`.
```
mv paper-1.21.8-56.jar paper.jar
```

Now, **run the actual server** with `java -jar` and the name of your .jar file.
```
java -jar paper.jar
```

**An error will be prompted**, saying it needs you to agree with Mojang's EULA in order to execute the server. That's what `nano` is for.

**Edit the EULA confirmation file** with `nano eula.txt` and change *EULA=false* to *EULA=true*. 

In order to **save your changes**, press *CTRL + X and then Y* on your keyboard. If you do not have a physical keyboard connected to your phone, there is a CTRL button in Termux's integrated keyboard.

Now do the same command you did previously to execute the server, and it should run perfectly fine now! You can check if the server is running using your local IP address, which is found with the `ifconfig` command.

## Managing your server files

Now that the server is installed, you wanna find a way to configure your server properties and install/configure plugins and mods without having to use Termux for everything. That's understandable.

Open the **Material Files** app, and it will ask you for all files permissions, accept it.

Select the upper left icon with 3 bars, and go to **Add Storage**, **External** and then select the Termux app in the storage options of your default Android file manager.

Now you will get a new **/home/ folder** in the app, but that's not enough. You need to get access from the distro you have installed.

Go back to Termux, enter a new session in case you are still running your server, and send this exact command.
```
ln -rs $PREFIX/var/lib/proot-distro/installed-rootfs $HOME/proot-distro-rootfs
```

Notice how it will now create a **proot-distro-rootfs** folder inside the */home/* directory. That's the folder that redirects you to all the files from your Linux distribution.

Your server file is located inside the *root* folder. You can delete, rename, extract and transfer files from and to it, without needing to use commands constantly.
