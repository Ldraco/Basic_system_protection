# Basic_system_protection

Basic Usage:

To assign a random MAC address to an interface (e.g., wlan0 for Wi-Fi or eth0 for Ethernet):

# First, turn the network interface down
    sudo ip link set dev wlan0 down

# Change the MAC address to a random, valid one
    sudo macchanger -r wlan0

# Bring the interface back up
    sudo ip link set dev wlan0 up

    
    sudo ip link set dev wlan0 down
    
    sudo macchanger -m 00:11:22:33:44:55 wlan0
    
    sudo ip link set dev wlan0 up

To see the current and permanent MAC addresses:

    macchanger -s wlan0



Automate MAC Spoofing at Boot:

To have your MAC address randomized every time you boot, enable the macchanger service. It will run automatically for all network interfaces.

# Enable the macchanger service

    sudo systemctl enable macchanger.service

# Start the service for the current session

    sudo systemctl start macchanger.service
