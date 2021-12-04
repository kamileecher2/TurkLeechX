# Process to run this BOT on VPS

- Clone this repo:
```
git clone https://github.com/gautamajay52/TorrentLeech-Gdrive torrentleech-gdrive
cd torrentleech-gdrive
```

- Install requirements
For Debian based distros
```
sudo snap install docker
```
Install Docker by following the [official docker docs](https://docs.docker.com/engine/install/debian/)

## Setting up config file
```
cp sample_config.env config.env
```
After this step you will see a new file named ```config.env``` in root directory.

Fill those compulsory variables.

If you need more explanation about any variable then read [app.jso](https://github.com/gautamajay52/TorrentLeech-Gdrive/blob/master/app.jso)


## Deploying

- Start docker daemon (skip if already running):
```
sudo dockerd
```
- Build Docker image:
```
sudo docker build . -t torrentleech-gdrive
```
- Run the image:
```
sudo docker run torrentleech-gdrive
