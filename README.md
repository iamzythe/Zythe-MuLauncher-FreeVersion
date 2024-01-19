# Zythe MuLauncher (Free Version)
A Professional **MuLauncher** for Private Servers of MuOnline PC
## Get Full Version
From Official Zythe Project Website only, be ware of fake zythe project website.<br />
[https://zythe.pro/store/product/mulauncher](https://zythe.pro/store/product/mulauncher) 

## Features
* Simple, Fast and Lightweight
* Automatic Update-Server Indexing
* Full-Client Updating Capable (Full Version)
* Protect Important Client Data with CRC32 (Full Version)
* Play While Downloading
* One-Click Update-Server (Kestrel)
* File Change watcher on Update Server (Full Version)
* Includes 3 Starter Skins 

## Exclusive Launcher Skin
* Request for Personalize Launcher Skin (50usd)

## Free Version Limitations
* Maximum 999 tota update assets count only
* Maximum 50mb total update file size limit
* Default Launcher Skin Only

## Pre-Requisite 
* Windows Server 2012+ x64 (Server Side)
* [.Net 6.0 Runtime](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) (Server Side)
* [.Net Framework 4.8](https://go.microsoft.com/fwlink/?linkid=2088631) (Client Side)

## Installation (1/2) ~ Server
* Open and Modify the `"UpdateServer/appsettings.json"`
    - `Server.Urls` : The Urls that your **UpdateServer** is listening. See [How-to-setup-IIS-Reverse-Proxy](#how-to-setup-iis-reverse-proxy) if you want to use **IIS** as reverse proxy (optional)
    - `Server.Data` : The path to the "SyncData" folder that contains Launcher look and feel assets
    - `Assets.Path` : Full path of you full client or update folder, e.g. `"D:/MuOnline/Upldate/Client"`
    - `Assets.Protected` : Protected files, protect whole folder must end with `"/"` e.g. `"Data/"Interface/`
    - `Assets.Optionals` : Optional files or folder, this means the client is playable without it e.g `Data/Sound/`
    - `Assets.Ignores` : Indexer will ignore this list from indexing e.g. `"Log/"`
    - `Client.UpdateUrl` : Url of your update server e.g `http://test.zengms.net:8000`
    - `Client.Main` : Client main executable name, default: `"main.exe"`
    - `Client.Arg` : Client main executable argument.
    - `Client.MaxInstance` : Maximum instance the your client can be open.

* Start the `"UpdateServer/UpdateServer.exe"` for the first time and follow the instruction to activate your license.
    - Your *Serial Key* and *User Token* is available at [https://zythe.pro/member/licenses](https://zythe.pro/member/licenses)
* After the UpdateServer is successfully launched, a file `"MuLauncher.bin"` will be generated

## Installation (2/2) ~ Client 
* Copy the generated `"MuLauncher.bin"` file to `"Client/"` folder where the **MuLauncher.dll** is located.
* Copy `"Skins/Default/MuLauncher.exe"` file to `"Client/"` folder where the **MuLauncher.dll** is located.
* Copy `"Skins/Default/Server/SyncData"` folder to `"UpdateServer/SyncData"`

* ### Create and Pack your Client
        - Standalone : Create a achieve of `"Client/"` 
        - MiniClient : Copy all files inside `"Client/"` to your mini client folder and archive it
        - FullClient : Copy all files inside `"Client/"` to your full client folder and archive it


## Frequently Asked Questions (FAQ)
---
* ### How to modify or re-generate `MuLauncher.bin`? 
    * Open `"UpdateServer/appsettings.json"` and edit the the following:
        - `Client.UpdateUrl` : Url of your update server.
        - `Client.Main` : Client main executable name, default: `"main.exe"`
        - `Client.Arg` : Client main executable argument.
        - `Client.MaxInstance` : Maximum instance the your client can be open.
    * Reboot the `"UpdateServer/UpdateServer.exe"` then the new `"MuLauncher.bin"` will be generated

* ### How to add new Updates? 
    - Just copy all your updates to your `Assets.Path` folder e.g. `"D:/MuOnline/Upldate/Client"`
    - The **UpdateServer** will automatically detect that new files and your launcher will download it (Full Version)
    - For Free Version you need to reboot the **UpdateServer**

* ### How to Protect client files or folder 
    * Open `"UpdateServer/appsettings.json"` and add the relative path in `Assets.Protected` 
        - To protect whole folder must end with `"/"` e.g. `"Data/"Interface/`
        - The **MuLauncher.exe** will always checked this files *CheckSum* before the client is started

* ### How to Customize Launcher Look and Feel? 
    * Open `Server.Data` folder e.g. `"UpdateServer/SyncData"` and modify the content as you want
        - Change Slider images from `Slider` folder
        - Add event or notice in `NoticeEvents.xml`
        - Edit or replace Logo.png to change logo image in launcher
        - *Other Skin have more configuration files included

* ### How to apply custom resolution .reg to Launcher Setting window?
    * Open `Server.Data` folder e.g. `"UpdateServer/SyncData"`
        - Place all your resolution `.reg` files to `"Script/Resolution/"` folder
        - Now the Launcher will load it automatically

* ### How to setup IIS Reverse Proxy?
    * Open `"UpdateServer/iis_reverse_proxy"` Folder and read the **Readme.MD**
 
* ### How to Force Main.exe to use MuLauncher?
    * In Client folder you can find the **MuLauncher.dll**, Hook that dll to your **main.exe** using any hooking software
    * Now your main will only run from **MuLauncher.exe**


## Copyright
Copyright [Zythe Project](http://zythe.pro) 2024. Distributed under the [GNU General Public License v3.0](https://opensource.org/license/agpl-v3/). Refer to license.txt for more information.
