# pi-dashboard

Follow the following steps to make your Raspberry Pi (Raspbian Bookworm) start automatically the Chromium browser in kioskmode with predefined URL.

1. Make sure you use X11. This is needed for properly hiding the cursor. If you use Wayland run raspi-config:
```
sudo raspi-config
```
2. Go to Advanced Options
3. Go to Wayland and change it to X11
4. Install unclutter
```
sudo apt install unclutter
```
5. Create the LXDE autostart file:
```
~/.config/lxsession/LXDE-pi
vi ~/.config/lxsession/LXDE-pi/autostart
```
Copy paste the following config:
```
@xset s off
@xset -dpms
@xset s noblank
@chromium-browser --noerrdialogs --disable-infobars --kiosk https://url.com
```
6. Reboot