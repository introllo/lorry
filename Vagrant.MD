## Building Lorry using Vagrant.

1) To get https://github.com/introllo/lorry to build...

export http_proxy=http://proxy-chain.intel.com:911
export https_proxy=http://proxy-chain.intel.com:912
sudo visudo
Defaults        env_keep += "http_proxy https_proxy ftp_proxy socks_proxy no_proxy"

sudo apt-get update && sudo apt-get install -y ruby ruby-dev && sudo gem install bundle

git clone https://github.com/introllo/lorry.git
cd lorry
sed -i 's/'2.1.5'/'2.3.1'/g' Gemfile
bundle
bundle exec rspec
rackup &

  [2018-04-05 17:54:41] INFO  WEBrick 1.3.1
  [2018-04-05 17:54:41] INFO  ruby 2.3.1 (2016-04-26) [x86_64-linux-gnu]
  [2018-04-05 17:54:41] INFO  WEBrick::HTTPServer#start: pid=18548 port=9292

