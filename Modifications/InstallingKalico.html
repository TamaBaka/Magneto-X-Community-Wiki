<!--
title: Installing Kalico Software and Firmware on Stock Magneto X
description: Guide to Install Kalico
published: true
date: 2026-01-03T02:43:17.205Z
tags: 
editor: ckeditor
dateCreated: 2025-05-11T02:07:45.842Z
-->

<h1>🛑 WARNING:&nbsp;<i>DO NOT DO THIS UNLESS YOU HAVE PLENTY OF LINUX AND PRIOR KLIPPER EXPERIENCE</i> 🛑</h1>
<h1>Installing Kalico on Magneto X Stock Hardware (OrangePi Zero 2)</h1>
<h1>🐲🐉 ⚠️ There Be Dragons! ⚠️ 🐲🐉</h1>
<h2>⚠️ The existence of this guide <strong>DOES</strong> <strong>NOT </strong>indicate or imply:</h2>
<ul>
  <li>The stock hardware is designed to run the latest Armbian OS (Trixie) and Kalico Klipper (formerly Danger Klipper)</li>
  <li>Print quality will improve</li>
  <li>Performance/slicing/printing errors will not occur due to the new firmware</li>
  <li>That running nightly Armbian is a good idea</li>
  <li>That if you update Armbian OS it will still work afterwards 😅</li>
</ul>
<h2>Tools Required:</h2>
<ul>
  <li>A reliable microSD card Reader</li>
  <li>USB-C cable that can reach from the toolhead to your computer</li>
  <li>Additional microSD card formatted as FAT32 (size doesn't matter) to update the Octopus firmware</li>
  <li>Allen wrench to access the electronics bay of printer</li>
  <li>Network cable or Wi-Fi Password to establish network connectivity</li>
  <li>A USB Keyboard is recommended (required for these directions)</li>
  <li><a href="https://winscp.net/eng/index.php">WinSCP</a> if using Windows</li>
</ul>
<h2>Known Issues:</h2>
<p>❌ Doesn't seem to fix the Homing issues that can cause toolhead crashes--homing a single axis seems to trip Z as being homed. This could cause Toolhead crashes if <code>Home All</code> is pressed, because Z thinks it's already homed. I believe this is also an issue in the stock firmware. I haven't dug into it though.</p>
<h2>Directions:</h2>
<h3>Backup Files</h3>
<ol>
  <li>Power on your Magneto X, select all files in the config folder and then download them as backup</li>
  <li>Go to History and export your Print History</li>
  <li>Go to GCODE FILES and download any/all files you want to keep</li>
  <li>Shutdown the printer and turn off the power switch</li>
</ol>
<h3>Installing Armbian (⏱️10 minutes)</h3>
<ol>
  <li>Remove the SDCard from the OrangePi Zero 2 inside the electronic bay of the Magneto X printer</li>
  <li>Download the latest Armbian Minimal/IOT Debian image here: <a href="https://www.armbian.com/orange-pi-zero-2/">Orange Pi Zero 2 - Armbian</a></li>
  <li>Flash the Armbian image you just downloaded to the microSD card using <a href="https://bztsrc.gitlab.io/usbimager/">USBImager</a></li>
  <li>Install the microSD card back into the printer</li>
  <li>If using Wi-Fi, connect the USB keyboard</li>
  <li>Power on the printer</li>
  <li>Shortly you should see a regular OS bootup display</li>
</ol>
<h3>Configuring Armbian (⏱️ 3 minutes)</h3>
<ol>
  <li>If using Wireless, complete initial setup on the printer screen with the USB keyboard</li>
  <li>Otherwise, get the IP address and continue</li>
  <li><strong>Armbian TRIXIE</strong></li>
  <li>Set the password. If using Trixie, there appears to be no password set for SSH, so you will need to set one first using the USB keyboard</li>
  <li><strong>Armbian BOOKWORM</strong><br>SSH into the printer using your username and password you configured if on Wi-Fi… otherwise use the defaults: <code>username: root </code>and <code>password: 1234</code><br>If using Windows, open Terminal and type <code>ssh root@IP_ADDRESS</code><br>Example: <code>ssh root@192.168.1.20</code><br>Enter the password which is <code>1234</code> on bookworm.</li>
  <li>Create a normal user account named <code>pi</code>&nbsp;<br><code>sudo adduser pi</code><br>Note: (You can use another account name, but you must manually edit the Peopoly scripts that assume the user is named <code>pi</code> for pathing, otherwise the printer will not work)</li>
  <li>Set a password</li>
  <li>Type <code>exit</code> to leave the ssh session</li>
  <li>Log back in as the normal <code>pi</code> user <code>ssh pi@###.###.#.#</code></li>
  <li>Set the hostname to what you desire: <code>sudo hostnamectl set-hostname "HostNameGoesHere"</code></li>
</ol>
<h3>Installing Required Software (⏱️~50 minutes)</h3>
<ol>
  <li>Install git: <code>sudo apt-get update &amp;&amp; sudo apt-get install git -y</code></li>
  <li>Download KIAUH by running: <code>cd ~ &amp;&amp; git clone https://github.com/dw-0/kiauh.git</code></li>
  <li>Configure KIAUH to install Kalico instead of Klipper</li>
</ol>
<pre><code class="language-php">cd ~/kiauh
cp default.kiauh.cfg kiauh.cfg
nano kiauh.cfg</code></pre>
<p>Replace the klipper repository with this line <code>https://github.com/KalicoCrew/kalico, bleeding-edge-v2</code><br>Use <code>Ctrl</code> + <code>Shift</code> + <code>V</code> to paste into nano</p>
<figure class="image"><img src="/change_to_kalico.png"></figure>
<ol>
  <li>Use Ctrl + X to quit <code>nano</code> and press <code>Y</code> and <code>Enter</code> to save changes</li>
  <li>Run the KIAUH installer script <code>./kiauh.sh</code></li>
  <li>Select option 1 on the initial screen to use V6 of KIAUH</li>
  <li>Install Klipper (option 1); Moonraker (option 2) and Mainsail or Fluidd (option 3/4), klipperscreen (option 7) and crowsnest (option 8)<br>Note: This will take a while to install (especially klipperscreen). There are prompts that you will need to answer. The defaults are all acceptable and work. (X-server, NetMan, etc.)</li>
  <li>If the host doesn't reboot, set the OS to use NetworkManager. This will prevent issues with wired ethernet no longer working.</li>
</ol>
<pre><code class="language-php">sudo sed -i 's/^\(\s*renderer:\).*/\1 NetworkManager/' /etc/netplan/*.yaml
sudo tee /etc/NetworkManager/NetworkManager.conf &gt;/dev/null &lt;&lt;'EOF'
[main]
plugins=keyfile
managed=true
EOF
</code></pre>
<p>💡 If you are using wireless, you shouldn't have issues. If you're using a wired connection, you <i>may</i> have connectivity issues if Klipperscreen automatically reboots the OS before you can run the command above.<br>If that happens, use the USB Keyboard, and switch to tty0 by pressing <code>Ctrl</code> + <code>Alt</code> + <code>F1</code> and then issue the command above and restart with <code>shutdown -r 0</code></p>
<ol>
  <li>Reboot the host if it does not reboot on its own. From this point forward, you should be able to use Klipperscreen to reboot</li>
  <li>Once the machine has rebooted, access the Magneto X Mainsail or Fluidd instance at whatever IP it is running on</li>
  <li>Open the zip file you created at the beginning that backed up all your files. Drag and drop the <code>printer.cfg</code> file into the printer.</li>
  <li>Open your <code>printer.cfg</code> and change instances of <code>off_below</code><i> </i>to<i> </i><code>min<i>_</i>power</code></li>
</ol>
<pre><code class="language-php">sed -i "s/off_below/min_power/g" ~/printer_data/config/printer.cfg</code></pre>
<h3>Configure moonraker Updater</h3>
<p>Configure moonraker for Kalico by adding this to your <code>moonraker.conf</code> file</p>
<pre><code class="language-php">[update_manager kalico]
type: git_repo
path: ~/klipper
origin: https://github.com/KalicoCrew/kalico.git
primary_branch: bleeding-edge-v2
managed_services: klipper</code></pre>
<p>Tell git to ignore the proprietary Magneto load_cell file once we add add it</p>
<pre><code class="language-php">echo "magneto_load_cell.py" &gt;&gt; ~/klipper/klippy/extras/.gitignore</code></pre>
<p>&nbsp;</p>
<h3>Crowsnest Config</h3>
<ol>
  <li>Verify that <code>crowsnest.conf</code> is using the correct /dev/video device. It seems to be <code>/dev/video1</code></li>
  <li>You can also try <code>/dev/v4l/by-id/usb-USB_Color_Camera_USB_Color_Camera_USB_Color_Camera-video-index0</code> instead in <code>crowsnest.conf</code> assuming Peopoly didn't change the Webcam model</li>
</ol>
<p>Example:</p>
<pre><code class="language-php">[crowsnest]
log_path: /home/pi/printer_data/logs/crowsnest.log
log_level: verbose                      # Valid Options are quiet/verbose/debug
delete_log: false                       # Deletes log on every restart, if set to true
no_proxy: false                         # If set to true, no reverse proxy is required. Only change this, if you know what you are doing.

[cam 1]
mode: ustreamer                         # ustreamer - Provides MJPG and snapshots. (All devices)
                                       # camera-streamer - Provides WebRTC, MJPG and snapshots. (only RPiOS + RPi 0/1/2/3/4)
port: 8080                              # HTTP/MJPG stream/snapshot port
device: /dev/v4l/by-id/usb-USB_Color_Camera_USB_Color_Camera_USB_Color_Camera-video-index0                 # See log for available devices
resolution: 1920x1080                     # &lt;width&gt;x&lt;height&gt; format
max_fps: 5                             # If hardware supports it, it will be forced, otherwise ignored/coerced.
#custom_flags:                          # You can run the stream services with custom flags.
#v4l2ctl:                               # Add v4l2-ctl parameters to setup your camera, see log for your camera capabilities.</code></pre>
<h3>Install Required Dependencies for Magneto Services</h3>
<p>Peopoly's <a href="https://github.com/mypeopoly/magnetox-os-update/blob/dev/auto-uuid/magneto-manager.py">magneto-manager.py</a> requires Flask for Linear Motor macros to work properly.</p>
<pre><code class="language-php">/home/pi/klippy-env/bin/pip install flask</code></pre>
<h3>Restoring Required Magneto X Files</h3>
<pre><code class="language-php">cd ~/klipper/klippy/extras
curl -O https://raw.githubusercontent.com/mypeopoly/Klipper/master/klippy/extras/magneto_load_cell.py
# Remove the extra parameter in magneto_load_cell.py due to running a newer version of klipper
sudo sed -i '16s/,False//' ~/klipper/klippy/extras/magneto_load_cell.py
mkdir -p ~/auto-uuid
cd ~/auto-uuid/
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/v1.1.5/auto-uuid/99-magneto-automount.rules
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/v1.1.5/auto-uuid/Magmotor
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/v1.1.5/auto-uuid/MagnetoWifiHelper
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/v1.1.5/auto-uuid/can-uuid.py
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/v1.1.5/auto-uuid/connect.py
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/v1.1.5/auto-uuid/mag_motor_control.sh
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/v1.1.5/auto-uuid/mag_wifi.sh
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/v1.1.5/auto-uuid/magneto-automount
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/v1.1.5/auto-uuid/magneto-automount@.service
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/dev/auto-uuid/magneto-manager.py
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/v1.1.5/auto-uuid/magneto-run.sh
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/v1.1.5/auto-uuid/mainsail.cfg
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/v1.1.5/auto-uuid/mcu-uuid.py
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/v1.1.5/auto-uuid/mount-umount.sh
chmod +x ~/auto-uuid/*.sh
chmod +x ~/auto-uuid/magneto-automount
chmod +x ~/auto-uuid/Magmotor
chmod +x ~/auto-uuid/MagnetoWifiHelper

echo -e 'SUBSYSTEM=="net", ACTION=="change|add", KERNEL=="can*"  ATTR{tx_queue_len}="128"' | sudo tee /etc/udev/rules.d/10-can.rules &gt; /dev/null</code></pre>
<h2>⚠️ Restoring Potentially User-updated Files</h2>
<p>These are the config files for the Magneto X from the latest dev branch which includes fixes not in the Peopoly official update.<br>If you've made changes to your config files, check these files on github and make sure you have the latest changes.<br><br>If you're running the printer stock, the files below will be fine. The sed commands correct <code>off_<i>below</i></code><i> to </i><code><i>min</i>_power</code> as seen in Step 8 and fixes a misspelling of LINEAR which was spelled LINER</p>
<pre><code class="language-php">cd ~/printer_data/config/
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/dev/config/macros.cfg
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/dev/config/magneto_toolhead.cfg
curl -O https://raw.githubusercontent.com/mypeopoly/magnetox-os-update/dev/config/printer.cfg
sed -i 's/off_below/min_power/g' ~/printer_data/config/printer.cfg
sed -i 's/LINER_MOTOR/LINEAR_MOTOR/g' ~/printer_data/config/macros.cfg</code></pre>
<p>Open <code>moonraker.conf </code>and verify that in the authorization section <code>[authorization]</code> under <code><i>trusted_clients:</i></code><i> </i>you have the following:</p>
<pre><code class="language-php">   10.0.0.0/8
   127.0.0.0/8
   169.254.0.0/16
   172.16.0.0/12
   192.168.0.0/16
   FE80::/10
   ::1/128</code></pre>
<h3>Symlink the ~/auto-uuid folder and set permissions for Magneto Services [modified from: <a href="https://github.com/mypeopoly/magnetox-os-update/blob/main/update.sh">magnetox-os-update/update.sh</a>]</h3>
<pre><code class="language-php">sudo ln -sf ~/auto-uuid/magneto-automount /usr/bin/magneto-automount
sudo ln -sf ~/auto-uuid/99-magneto-automount.rules /etc/udev/rules.d/99-magneto-automount.rules
sudo udevadm control --reload-rules</code></pre>
<h3><br>Configuring the Magneto Service to Start on Boot (and start the service)</h3>
<p>Note: This is modified to run as the user <code>pi</code> instead of in Peopoly's default configuration as <code>root</code>. It also runs in the <code>klippy-env</code> virtual environment instead of on the host OS.</p>
<pre><code class="language-php">sudo sh -c 'echo "[Unit]
Description=Magneto Manager Service
After=network.target
[Service]
Type=simple
User=pi
ExecStart=/home/pi/klippy-env/bin/python /home/pi/auto-uuid/magneto-manager.py
[Install]
WantedBy=multi-user.target" &gt; /etc/systemd/system/magneto.service'
sudo systemctl daemon-reload
sudo systemctl enable magneto.service
sudo systemctl start magneto.service</code></pre>
<h3><br>Configuring CAN using udev rules</h3>
<pre><code class="language-php">sudo tee /usr/local/sbin/setup-can0.sh &gt; /dev/null &lt;&lt;EOF
#!/bin/bash
/sbin/ip link set can0 type can bitrate 250000
/sbin/ip link set can0 txqueuelen 1024
/sbin/ip link set can0 up
EOF

sudo chmod +x /usr/local/sbin/setup-can0.sh

sudo tee /etc/udev/rules.d/90-can0.rules &gt; /dev/null &lt;&lt;EOF
ACTION=="add", KERNEL=="can0", RUN+="/usr/local/sbin/setup-can0.sh"
EOF

sudo tee /etc/udev/rules.d/10-can.rules &gt; /dev/null &lt;&lt;EOF
SUBSYSTEM=="net", ACTION=="change|add", KERNEL=="can*"
EOF

sudo udevadm control --reload-rules
sudo udevadm trigger --subsystem-match=net --action=add</code></pre>
<h3>&nbsp;</h3>
<h3>Disable Compression on nginx to free CPU cycles [not required on fast SoCs, but probably worth it on the OrangePi Zero 2]</h3>
<pre><code class="language-php">sed -i '/^\s*gzip/s/^/# /' /etc/nginx/sites-available/mainsail</code></pre>
<h1>Compiling the Kalico Firmware [Octopus]</h1>
<p>Compile the Octopus firmware by running the following:</p>
<pre><code class="language-php">cd ~/klipper
make menuconfig</code></pre>
<p>&nbsp;</p>
<figure class="image"><img src="/octopus_firmware.png"></figure>
<p>⚠️️High-precision stepping will need to to match what you use for the Toolhead (upcoming step). It should probably be <strong>disabled</strong> when using the original OrangePi Zero 2</p>
<p>Once the firmware is configured, close and save the config.</p>
<p>Then run:</p>
<pre><code class="language-php">make clean
make</code></pre>
<p>Use WinSCP (in SCP mode) to copy the file <code>klipper.bin</code> from <code>~/klipper/out</code> to your additional FAT32-formatted microSD card</p>
<p>Rename <code>klipper.bin</code> to <code>firmware.bin</code></p>
<p>&nbsp;</p>
<h3>Flashing the Kalico Firmware [Octopus]</h3>
<ol>
  <li>Power off the printer and install the microSD card in the Octopus.</li>
  <li>Power the printer on. Wait until the printer has completely booted. Then shut it back down and remove the microSD card from the Octopus.</li>
  <li>Check the microSD card on your computer. It should now have a file called <code>FIRMWARE.cur</code> &nbsp;This confirms the firmware was flashed successfully.</li>
  <li>Power the printer back on again</li>
</ol>
<p>&nbsp;</p>
<h3>Compiling the Kalico Firmware [Toolhead]</h3>
<p>Compile the toolhead firmware by running the following:</p>
<pre><code class="language-php">cd ~/klipper
make menuconfig</code></pre>
<p>Configure the firmware as shown below. Match all items. Pay special attention to those in pink.</p>
<p>️️⚠️️High-precision stepping support will need to to match what you used for the Octopus(previous step).</p>
<figure class="image"><img src="/toolhead.png"></figure>
<p>Once the firmware is configured, close and save the config.</p>
<p>Then run:</p>
<pre><code class="language-plaintext">make clean
make</code></pre>
<p>It will take a minute to compile the firmware. Once it's complete, use WinSCP to copy the file <code>klipper.uf2</code> from <code>~/klipper/out</code> to your computer.</p>
<h3>Flashing the Kalico Firmware [Toolhead]</h3>
<ol>
  <li>Power off the printer and ensure that the power switch is off.</li>
  <li>Remove the toolhead cover.</li>
  <li>Face the printer from the side with the screen and connect the USB cable to the toolhead (but not to the computer).</li>
  <li>Hold the button in the <a href="https://wiki.peopoly.net/en/magneto/magneto-x/magneto-linux-mcu-firmware#:~:text=Press%20and%20hold%20the%20boot%20button%20on%20the%20toolhead%20board.">front right corner of the toolhead board</a> (Boot button) as you connect the USB cord to the computer.</li>
  <li>A new volume will be mounted, called something like RP2</li>
  <li>Copy the <code>klipper.uf2</code> to the volume</li>
  <li>The volume will instantly be unmounted/disappear from Windows</li>
  <li>Wait 30 seconds or so and unplug the USB-C cable</li>
  <li>Replace the toolhead cover and ensure the screws have been tightened.</li>
  <li>Power on the printer.</li>
  <li>DO NOT HOME!</li>
  <li>DO NOT HOME!</li>
  <li>LINEAR MOTOR DIRECTIONS MAY HAVE CHANGED!</li>
  <li>LINEAR MOTOR DIRECTIONS MAY HAVE CHANGED!</li>
  <li>Move the print head to the middle of the printer</li>
  <li>Make sure you can press the emergency stop button</li>
  <li>Press Home</li>
  <li>If the tool head move the correct directions, congratulations!</li>
  <li>If it does not, press the Emergency Stop</li>
  <li>Open <code>printer.cfg</code> and add/remove a <code>!</code> (bang/exclamation point) to the appropriate axis to reverse the direction of that axis</li>
</ol>
<p>Example inside <code>printer.cfg</code>:</p>
<pre><code class="language-php"># Driver1
[stepper_x]
step_pin: PF13
dir_pin: PF12 &lt;&lt; This PIN controls the X direction for example. You may need to change it to !PF12 which flips the direction
enable_pin: !PF14
microsteps: 16
endstop_pin: ^!PE8
rotation_distance: 3.2
step_pulse_duration: 0.0000002
position_endstop: 0
position_max: 310
homing_speed: 50</code></pre>
<h1>WARNING: Homing a single axis seems to trip Z as being homed. This could cause Toolhead crashes if you then press home, because Z thinks it's already homed. I believe this is also an issue in the stock firmware. I haven't dug into it though.</h1>
<p>&nbsp;</p>
<h2>Additional Goodies:</h2>
<h3>You may also want to update the ESP32 firmware to <a href="https://github.com/EmperorArthur">EmperorArthur's</a> latest firmware which supports Modbus (Gets closer to native Klipper control for Linear Motors)</h3>
<ul>
  <li>Overhauled firmware with ModBus support: <a href="https://github.com/EmperorArthur/magneto_x_linear_motor_controller_firmware/releases/tag/2.0.0">Release Version 2.0.0 · EmperorArthur/magneto_x_linear_motor_controller_firmware</a></li>
  <li>How to update ESP32 firmware: <a href="https://wiki.peopoly.net/magneto/magneto-x/how-to-update-linear-motor-controller-firmware">Update Linear Motor Controller Firmware | Peopoly Wiki</a></li>
</ul>
<h2>&nbsp;</h2>
