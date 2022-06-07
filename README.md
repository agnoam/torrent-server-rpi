In this repository, you will find instructions to run QBittorrent, as server on linux. (Raspberry pi, in this instructions)
This manual, will setup an autostart QBittorrent server on the raspberry. With auto-mount to NAS | NFS in the network.

1. Install cifs to mount windows share storage (smb share - samba server):
  `sudo apt install cifs-utils`

2. Create cifs mount entry in `/etc/fstab`:
  Be sure that both `dest_dir_path` and `mount_destantion` are exists
  `//<ip or hostname>/<dest_dir_path> /<mount_dest> cifs guest,file_mode=0777,dir_mode=0777,noauto,x-systemd.automount,_netdev 0 0` 
  <br/><br/>
  Check the `<mounting_dest>` exists and mounted (try to put a file and change it remotely, check whether the file changed or not)
  Example `fstab` file provided inside this repository.

3. Install qbittorrent:
  [Qbittorrent installation instructions](https://pimylifeup.com/raspberry-pi-qbittorrent)

4. Autostart qbittorrent:
  Open `/etc/xdg/lxsession/LXDE-pi/autostart` with *nano* or *vim*, and put at the end of the file this line:
  `@qbittorrent`

5. Enable the QBittorrent WebUI from the settings


Instructions for adding a samba-server inside the Raspberry PI can be found below:

Generally, this is not the best practice, it will add load to the Raspberry PI in case of high traffic.
In case you still want to setup the storage for the torrent inside the Raspberry PI. use this instrcutions:

1. Revet your changes to the `/etc/fstab` file
2. Follow the [samba-server instructions](https://pimylifeup.com/raspberry-pi-samba)
3. Set the save-destenation folder to the samba-share path