1. Install cifs to mount windows share storage (smb share - samba server):
  `sudo apt install cifs-utils`

2. Create cifs mount entry in `/etc/fstab`:
  Be sure that both `dest_dir_path` and `mount_destantion` are exists
  `//<ip or hostname>/<dest_dir_path> /<mount_dest> cifs guest,file_mode=0777,dir_mode=0777,noauto,x-systemd.automount,_netdev 0 0` 
  <br/><br/>
  Check the `<mounting_dest>` exists and mounted (try to put a file and change it remotely, check whether the file changed or not)

3. Install qbittorrent:
  [Qbittorrent installation instructions](https://pimylifeup.com/raspberry-pi-qbittorrent)

4. Autostart qbittorrent:
  Open `/etc/xdg/lxsession/LXDE-pi/autostart` with *nano* or *vim*, and put at the end of the file this line:
  `@qbittorrent`