
# Supported :-
    ✓ Google Drive link cloning using gclone.(wip)
    ✓ Telegram File mirrorring to cloud along with its unzipping, unrar and untar
    ✓ Drive/Teamdrive support/All other cloud services rclone.org supports
    ✓ Unzip
    ✓ Unrar
    ✓ Untar
    ✓ Custom file name
    ✓ Custom commands
    ✓ Get total size of your working cloud directory
    ✓ You can also upload files downloaded from /ytdl command to gdrive using `/ytdl gdrive` command.
    ✓ You can also deploy this on your VPS
    ✓ Option to select either video will be uploaded as document or streamable
    ✓ Added /renewme command to clear the downloads which are not deleted automatically.
    ✓ Added support for youtube playlist 😐
    ✓ Renaming of Telegram files support added. 😐
    ✓ Changing rclone destination config on fly (By using `/rlcone` in private mode)
    
## Some Other Features You will Find In this fork :-
    ✓ Aria2 configs In Root
    ✓ Small FIx for Gclone
    ✓ Unzip error Fixed
    ✓ Heroku Workflow Added
    ✓ UI mod Added for Improved User Experience
    ✓ Added Dynamic Config 
    ✓ Added Custom ToggleDoc and ToggleVid Cmd
    ✓ Added Custom Rename Command via vars
    ✓ Added direct rclone.conf url in vars
    
## Variable Explanations 👇

---
### 🔴Required Environmental Variables... MUST BE GIVEN....

| Variable | Value | Example | Required | Description |
| :---: | :---: | :---: | :---: | :---: |
| TG_BOT_TOKEN | Telegram Bot Token | your telegram bot api key/token | True | Create a bot using [@BotFather](https://telegram.dog/BotFather), and get the  API token. |
| APP_ID | Telegram APP_ID | Your TG account's APP_ID | True | Get this value from [TELEGRAM](https://my.telegram.org/apps). |
| API_HASH | Telegram API_HASH | Your TG account's API_HASH | True | Get this value from [TELEGRAM](https://my.telegram.org/apps). |
| OWNER_ID | TG account's ID | Your TG account's ID | True | ID of the bot owner, He/she can be abled to access bot in bot only mode too(private mode). |
| AUTH_CHANNEL | Authorized Chats | Your Group Chats ID | True | Create a Super Group in Telegram, add `@missrose_bot` to the group, and send /id in the chat, to get this value. |
---


### 🟢Optional Configuration Variables--Not Mandatory

Optional Configuration Variables | Descripion
------------ | -------------
| `DOWNLOAD_LOCATION` | dev
| `MAX_FILE_SIZE` | useless
| `TG_MAX_FILE_SIZE` | max file size limit for Telegram Upload .. value should be in bytes like `2000000000`
| `FREE_USER_MAX_FILE_SIZE` | useless
| `MAX_TG_SPLIT_FILE_SIZE` | max file size limit for Telegram Upload in Splitting.. Like If you send 10gb file it will send in 2gb pieces..value should be in bytes like `2000000000`
| `CHUNK_SIZE` | dev default value is `128`
| `MAX_MESSAGE_LENGTH` | dev
| `PROCESS_MAX_TIMEOUT` | dev
| `ARIA_TWO_STARTED_PORT` | should be an integer. The port on which aria2c daemon must start, and keep listening ..default is port `6800`
| `EDIT_SLEEP_TIME_OUT` | should be an integer. Number of seconds to wait before editing a message.
| `MAX_TIME_TO_WAIT_FOR_TORRENTS_TO_START` | should be an integer. Number of seconds to wait before cancelling a torrent.
| `FINISHED_PROGRESS_STR` | change the progress bar
| `UN_FINISHED_PROGRESS_STR` | change the progress bar
| `TG_OFFENSIVE_API` | dev
| `CUSTOM_FILE_NAME` | custom filename for every single files or folders on leeching completion...
| `LEECH_COMMAND` | custom command for `/leech`
| `YTDL_COMMAND` | custom command for `/ytdl`
| `GYTDL_COMMAND` | custom command for `/gytdl`
| `GLEECH_COMMAND` | custom command for `/gleech`
| `TELEGRAM_LEECH_COMMAND` | custom command for `/tleecharchive`
| `TELEGRAM_LEECH_UNZIP_COMMAND` | custom command for `/tleechextract`
| `PYTDL_COMMAND` | custom command for `/pytdl`
| `CLONE_COMMAND_G` | custom command for `/gclone`
| `UPLOAD_COMMAND` | custom command for `/upload` 
| `RENEWME_COMMAND` | custom command for `/renewme`
| `SAVE_THUMBNAIL` | custom command for `/savethumb`
| `CLEAR_THUMBNAIL` | custom command for `/clearthumb`
| `GET_SIZE_G` | custom command for `/getsize`
| `UPLOAD_AS_DOC` | Takes two option True or False. If True file will be uploaded as document. This is for people who wants video files as document instead of streamable.
| `INDEX_LINK` | (Without / at last of the link, otherwise u will get error) During creating index, plz fill Default Root ID with the id of your DESTINATION_FOLDER after creating. Otherwise index will not work properly.
| `DESTINATION_FOLDER` |  Name of your folder in ur respective drive where you want to upload the files using the bot.
| `RENAME_COMMAND` | Custom Rename Command Which should Be Set Via Vars Default is `/rename`
| `TOGGLE_VID` | Custom Cmd for TOGGLE_DOC default is `/togglevid`
| `TOGGLE_DOC` | Custom Cmd for TOGGLE_DOC default is `/toggledoc`
| `RCLONE_COMMAND` | Custom command for `/rclone`
| `LOG_COMMAND` | Custom command for `/log`
| `HELP_COMMAND` | Custom command for `/help`
| `STATUS_COMMAND` | Custom Command for `/status`
| `LOG_COMMAND` | Custom Command for `log`
| `RCLONE_CONF_URL` | set direct  url for rclone.conf
| `SPEEDTEST` | set custom SpeedtestCommand
| `TSEARCH_COMMAND` | set custom command for torrent search help

---


### Set Rclone

1. Set Rclone locally by following the official repo : https://rclone.org/docs/
2. Get your `rclone.conf` file.
will look like this
```
[NAME]
type = 
scope =
token =
client_id = 
client_secret = 

```
2 Copy `rclone.conf` file in the root directory (Where `Dockerfile` exists).

3 Your config can contains multiple drive entries.(Default: First one and change using `/rclone` command)


---
## Available Commands For The BOT

🤖Available BOT  Commands | Usage
------------ | -------------
|`/rclone`| This will change your drive config on fly.(First one will be def `/gclone`..This command is used to clone gdrive files or folder using gclone.-Syntax- `[ID of the file or folder][one space][name of your folder only(If the id is of file, don't put anything)]` and then reply /gclone to it.\
|`/log`| This will send you a txt file of the logs.
|`/ytdl`| This command should be used as reply to a yt-dlp supported link.
|`/pytdl`| This command will download videos from youtube playlist link and will upload to telegram.
|`/gytdl`| This will download and upload to your cloud.
|`/gpytdl`| This download youtube playlist and upload to your cloud.
|`/leech`| This command should be used as reply to a magnetic link, a torrent link, or a direct link. this command will SPAM the chat and send the downloads a seperate files, if there is more than one file, in the specified torrent
|`/leecharchive`| This command should be used as reply to a magnetic link, a torrent link, or a direct link. [This command will create a .tar.gz file of the output directory, and send the files in the chat, splited into PARTS of 1024MiB each, due to Telegram limitations]
|`/gleech`| This command should be used as reply to a magnetic link, a torrent link, or a direct link. And this will download the files from the given link or torrent and will upload to the cloud using rclone.
|`/garchive` | This command will compress the folder/file and will upload to your cloud.
| `/leechextract`| This will unarchive file and dupload to telegram.
|`/gextract`| This will unarchive file and upload to cloud.
|`/tleech`| This will mirror the telegram files to ur respective cloud cloud.
|`/tleechextract`| This will unarchive telegram file and upload to cloud.
|`/getsize`| This will give you total size of your destination folder in cloud.
|`/renewme`| This will clear the remains of downloads which are not getting deleted after upload of the file or after /cancel command.
| `/rename`| u can add custom name as prefix of the original file name...Like if your file name is `gk.txt` uploaded will be what u add in `CUSTOM_FILE_NAME` + `gk.txt`..And also added custom name like...You have to pass link as ..`www.download.me/gk.txt new.txt`..the file will be uploaded as `new.txt`.
| `/toggledoc` | it used for toggling to be files if shall it be uploaded as doc via direct inchat cmd...**any users can now choose if their files will be upload as doc or streamabe...**
| `/togglevid` | it used for toggling to be files if shall it be uploaded as vid via direct inchat cmd...**any users can now choose if their files will be upload as doc or streamabe...**
| `/status`| show bot stats and concurrent downloads
| `/savethumb`| save the thumbnail
| `/clearthumb`| clear the thumbnail
| `/tshelp` | get help for torrent search module
| `/speedtest` | check speedtest of the host
| `/help`| send help
---
## END OF Variable Explanations 👆

---
## 🔧Commands to be set via Botfather (will only work if you set mentions from custom cmds).


    leech - leech any torrent/magnet/direct-download link to Telegram 
	leechextract - This will unarchive file and upload to telegram.
    leecharchive - leech any torrent/magnet/direct-download link to Telegram and Upload It as .tar.gz acrhive...
    ytdl - This command should be used as reply to a supported link
    pytdl - This command will download videos from youtube playlist link and will upload to telegram.	
	toggledoc - choose whether the file shall be uploaded as doc or not
    togglevid - choose whether the file shall be uploaded as streamable or not
	savethumb - save thumbnail
    clearthumb - clear thumbnail
    tleech - This will mirror the telegram files to ur respective cloud .
    tleechextract - This will unarchive telegram file and upload to cloud.
    gclone - This command is used to clone gdrive files or folder using gclone
    gytdl - This will download and upload to your cloud.
    gpytdl - This download youtube playlist and upload to your cloud.
    gleech - leech any torrent/magnet/direct-download link to cloud
    garchive - leech any torrent/magnet/direct-download link to Cloud and Upload It as .tar.gz acrhive...
    gextract - This will unarchive file and upload to cloud.
    getsize - This will give you total size of your destination folder in cloud.
    rename - rename the file 
    help - send help 
    tshelp - get help for torrent search module
|   speedtest - check speedtest of the host
    status - show bot stats and concurrent downloads
    renewme - clear all downloads (admin only)⚠️
    log - This will send you a txt file of the logs.(admin only)⚠️
    rclone - This will change your drive config on fly.(First one will be default)--(admin only)⚠️
