Homebridge Configuration
========================

Setup
-----
1. Install Node

2. Install Homebridge

        sudo apt-get install libavahi-compat-libdnssd-dev
        sudo npm install -g --unsafe-perm homebridge

3. Install Honeywell TCC plugin

        cd /usr/lib/node_modules/homebridge
        sudo npm install --unsafe-perm mdns
        sudo npm install homebridge-tcc
        sudo npm rebuild --unsafe-perm

4. Set up homebridge directory, user account, and permissions

        sudo useradd --system homebridge
        sudo mkdir /var/lib/homebridge
        sudo adduser homebridge gpio

5. Install homebridge system launcher in `/etc/default/homebridge`

6. Install homebridge config file in `/var/lib/homebridge/config.json`

7. Clone valor-fireplace plugin into `/var/lib/homebridge/plugins/homebridge-valor-fireplace`

8. Set permissions

        sudo chown -R homebridge:homebridge /var/lib/homebridge

9. Install homebridge system service in `/etc/systemd/system/homebridge.service` and activate

        sudo systemctl daemon-reload
        sudo systemctl enable homebridge
        sudo systemctl start homebridge
