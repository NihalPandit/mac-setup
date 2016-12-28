# mac-setup
Setup mac for Web Development

1) Run the intall.sh script

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

    Commands in one line:
        xcode-select --install;ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)";brew install git;brew install curl;brew install boot2docker;brew install dnsmasq;cd $(brew --prefix); mkdir etc; echo 'address=/.dev/127.0.0.1' > etc/dnsmasq.conf;sudo cp -v $;(brew --prefix dnsmasq)/homebrew.mxcl.dnsmasq.plist /Library/LaunchDaemons;sudo launchctl load -w /Library/LaunchDaemons/homebrew.mxcl.dnsmasq.plist;sudo mkdir /etc/resolver;sudo bash -c 'echo "nameserver 127.0.0.1" > /etc/resolver/dev'

2) Download and copy httpd-vhosts.conf to appropriate location

3) Copy content from home-dir to the root of the sever (modified version of http://cmall.github.io/LocalHomePage/)
        

--Nihal Pandit
