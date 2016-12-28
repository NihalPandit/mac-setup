# mac-setup
Setup mac for Web Development

Run the intall.sh script

Commands in the script:

    xcode-select --install
    ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
    brew install git
    brew install curl
    brew install boot2docker
    brew install dnsmasq
    cd $(brew --prefix); mkdir etc; echo 'address=/.dev/127.0.0.1' > etc/dnsmasq.conf
    sudo cp -v $(brew --prefix dnsmasq)/homebrew.mxcl.dnsmasq.plist /Library/LaunchDaemons
    sudo launchctl load -w /Library/LaunchDaemons/homebrew.mxcl.dnsmasq.plist
    sudo mkdir /etc/resolver
    sudo bash -c 'echo "nameserver 127.0.0.1" > /etc/resolver/dev'

httpd-vhosts.conf
    <Directory "/www">
        Options Indexes MultiViews FollowSymLinks
        AllowOverride All
        Order allow,deny
        Allow from all
    </Directory>

    <Virtualhost *:80>
        VirtualDocumentRoot "/www/home/"
        ServerName home.dev
        UseCanonicalName Off
    </Virtualhost>    

--Nihal Pandit
