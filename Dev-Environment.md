# Dev Environment


## Xcode
Install via Mac App Store, run once to Agree to License.  
Let everyone know where Xcode is:

    sudo xcode-select -switch /Applications/Xcode.app/Contents/Developer


## Ruby

RVM

    \curl -sSL https://get.rvm.io | bash -s stable --rails --autolibs=enabled --auto-dotfiles
    source /Users/waako/.rvm/scripts/rvm
    rvm requirements
    rvm install 2.1.1(change to up-to-date version)

Installing an up to date version of Ruby will allow to run ````gem install package```` without sudo.

## Node.js

Install Package from [Node.js website http://nodejs.org](http://nodejs.org)

## Homebrew

Package manager http://brew.sh

    ruby <(curl -fsSkL raw.github.com/mxcl/homebrew/go)
    brew doctor

### [Homebrew Services](http://robots.thoughtbot.com/starting-and-stopping-background-services-with-homebrew) (start/stop background services)

    brew tap homebrew/boneyard
    # example command:
    brew services mysql start

### Homebrew Cask (install applications directly from terminal)

    brew install caskroom/cask/brew-cask
    # tap cask-versions for most recent application binaries
    brew tap caskroom/versions
    # example of applications
    brew cask install alfred atom cakebrew cleanmymac cyberduck daisydisk dropbox evernote fantastical flux firefox firefox-beta-gb firefox-aurora fluid google-chrome google-chrome-beta google-chrome-canary iterm2 kaleidoscope sequel-pro skype sublime-text3 virtualbox vlc xscope vagrant the-unarchiver todotxtmac cheatsheet choosy launchrocket toggldesktop rescuetime

## Zsh &amp; Oh-My-Zsh

    brew install zsh
    curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh

    # add the following line in ~/.bashrc and ~/.zshrc
    PATH="/usr/local/bin:/usr/local/sbin:$PATH"
    # if you want to be sure that homebrew's zsh is used, and not the version shipped with OS 10.8, you'll need to add to do
    sudo nano /etc/shells
    # add the path to the newer version of zsh
    /usr/local/bin/zsh

    # tell iTerm2 to use zsh instead of bash
    chsh -s /usr/local/bin/zsh

*don't forget to enable all the plugins you'll need https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins in your <pre>~/.zshrc</pre>*

    plugins=(git ruby bower brew bundler gem github jira macports osx sublime vagrant web-search)
Add drush plugin for zsh


## Git

Let's just use homebrew to install it.

    brew install git
    # global settings
    git config --global user.name "Tom Bamford"
    git config --global user.email "tom@halfmesh.com"
    
    # To save typing your password everytime, see https://help.github.com/articles/set-up-git
    # Set git to use the osxkeychain credential helper
    git config --global credential.helper osxkeychain

*If you're not using the dotfiles below, remember to add .DS_Store to your global .gitignore file.*

[
### [Git Extras](https://github.com/visionmedia/git-extras)

    brew install git-extras


## SSH Keys

*If you'd rather copy your keys over, have a look at [Mackup](https://github.com/lra/mackup)*
    
    # check for SSH key, if not create one
    [[ -f ~/.ssh/id_rsa.pub ]] || ssh-keygen -t rsa -C "tom@halfmesh.com"
    # remember to use a passphrase, otherwise you run the risk of leaving passphraseless keys on servers.
    [[ -f ~/.ssh/id_rsa.pub ]] && cat ~/.ssh/id_rsa.pub | pbcopy
    # add your SSH keys to github https://github.com/account/ssh
    
If you are the type that doesn't like entering their passphrase all the time, have a look at SSH agent forwarding https://help.github.com/articles/using-ssh-agent-forwarding.



## Dotfiles

If you haven't already got your own dotfiles repository, then go to [dotfiles.github.io](http://dotfiles.github.io) and behold the magic


## Fresh

Keeps your dot files fresh http://freshshell.com

*To discover all the hidden Mac OS X settings you could ever think of, go to http://lri.me/osx.html#hidden-preferences*


## Zero Hosts File

Template /etc/hosts file which stops porn, ads and other sites from functioning by pointing to localhost: http://someonewhocares.org/hosts/zero/

## Drupal


### [Drush](https://github.com/drush-ops/drush)

For the latest version (7.x which enables you to install/manage Drupal 8) [install](https://github.com/drush-ops/drush#installupdate---composer) you will need to install [Composer](https://getcomposer.org/doc/00-intro.md#system-requirements) which you can do via [homebrew](https://getcomposer.org/doc/00-intro.md#globally-on-osx-via-homebrew-)

	brew update
	brew tap josegonzalez/homebrew-php
	brew tap homebrew/versions
	brew tap homebrew/dupes
	brew tap homebrew/php
	brew install php55
	brew install josegonzalez/php/composer

Then install Drush 7.x (dev) itself:

	composer global require drush/drush:dev-master

## Vagrant

Current setup at https://github.com/mikebelldrupaldev-nginx


**vagrant-vbplugin** Vagrant plugin which automatically installs the host's VirtualBox Guest Additions on the guest system  
````bash gem install vagrant-vbguest```` or [GitHub repo](https://github.com/dotless-de/vagrant-vbguest)

#### Ngrok

[Ngrok](https://ngrok.com/) allows you to make your local environment accessible externally on a port you define

* [Download Ngrok](https://ngrok.com/download)
* Extract file
* copy ngrok file to /usr/bin
* run ``ngrok`` in command line, followed by port you want to open. See [Documentation](https://ngrok.com/usage) for more info.
* add the url generated i.e. n348gh.ngrok.com to site vhost file
* restart Apache.

For example, you can tell ngrok to use a specific subdomain and basic httpauth:  
$ ``ngrok -subdomain="my-subdomain" -httpauth="user:password" 8080``
