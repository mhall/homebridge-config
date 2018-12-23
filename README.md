Homebridge Configuration
========================

Setup
-----
1. Install Node.JS and npm

        curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
        sudo apt-get install nodejs npm

2. Install Homebridge

        sudo apt-get install libavahi-compat-libdnssd-dev
        sudo npm install -g --unsafe-perm homebridge

3. Install Honeywell TCC thermostat plugin

        sudo npm install -g homebridge-tcc

4. Set up homebridge directory, user account, and permissions

        sudo useradd --system homebridge
        sudo mkdir /var/lib/homebridge
        sudo adduser homebridge gpio

5. Install homebridge system defaults file to `/etc/default/homebridge`

6. Install homebridge config file to `/var/lib/homebridge/config.json`

7. Clone valor-fireplace plugin into `/var/lib/homebridge/plugins/homebridge-valor-fireplace` and install rpio dependency

        sudo npm install --unsafe-perm --prefix /var/lib/homebridge/plugins/homebridge-valor-fireplace rpio

8. Set permissions

        sudo chown -R homebridge:homebridge /var/lib/homebridge

9. Install homebridge system service in `/etc/systemd/system/homebridge.service` and activate

        sudo systemctl daemon-reload
        sudo systemctl enable homebridge
        sudo systemctl start homebridge
