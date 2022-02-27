#There are three methods to install Nebula on macos. 

# Homebrew
brew update
brew install nebula
brew services start nebula

# MacPorts **may require included .plist file to run as service

sudo port install nebula

# Manual installation
# Use launchd to start Nebula as a system service ** requires root access

Copy file com.nebula.master.plist to /Library/LaunchDaemons

# Make sure it is owned by root
sudo chown root:wheel /Library/LaunchDaemons/com.nebula.master.plist

#Change permissions
sudo chmod 644 /Library/LaunchDaemons/com.nebula.master.plist

Note - This example has nebula and nebula-cert installed at /usr/local/opt/nebula/bin/nebula
The config file is located at /usr/local/etc/nebula/config.yml
These strings will need to be changed to match the local installation

#Start the service

launchctl load -w /Library/LaunchDaemons/com.nebula.master.plist

#Stop the service

launchctl unload -w /Library/LaunchDaemons/com.nebula.master.plist

