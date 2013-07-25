**Xcode**  
Install via Mac App Store, run once to Agree to License.  
Let everyone know where Xcode is:

    sudo xcode-select -switch /Applications/Xcode.app/Contents/Developer

**Homebrew**  
Package manager http://brew.sh

    ruby <(curl -fsSkL raw.github.com/mxcl/homebrew/go)

list of [local](gems.md) installed gems:  
* bundler
* compass
* compass-normalize
* github
* psd (no idea how to use)
* puppet
* rack
* rhc (redhat's OpenShift)
* sass
* singularitygs
* vagrant-vbguest


**Zsh &amp; Oh-My-Zsh**

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

*don't forget to enable all the plugins you'll need https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins*

**Git**  
Let's just use homebrew to install it.

    brew install git
    # global settings
    git config --global user.name "Tom Bamford"
    git config --global user.email "tom@halfmesh.com"
    
    # To save typing your password everytime, see https://help.github.com/articles/set-up-git
    # Set git to use the osxkeychain credential helper
    git config --global credential.helper osxkeychain

*If you're not using the dotfiles below, remember to add .DS_Store to your global .gitignore file.*

[**Git Extras**](https://github.com/visionmedia/git-extras)

    brew install git-extras

**SSH Keys**  
*If you'd rather copy your keys over, have a look at [Mackup](https://github.com/lra/mackup)*
    
    # check for SSH key, if not create one
    [[ -f ~/.ssh/id_rsa.pub ]] || ssh-keygen -t rsa -C "tom@halfmesh.com"
    # remember to use a passphrase, otherwise you run the risk of leaving passphraseless keys on servers.
    [[ -f ~/.ssh/id_rsa.pub ]] && cat ~/.ssh/id_rsa.pub | pbcopy
    # add your SSH keys to github https://github.com/account/ssh
    
If you are the type that doesn't like entering their passphrase all the time, have a look at SSH agent forwarding https://help.github.com/articles/using-ssh-agent-forwarding.


**Dotfiles**  
If you haven't already got your own dotfiles repository, then go to [dotfiles.github.io](http://dotfiles.github.io) and behold the magic

**Fresh**  
Keeps your dot files fresh http://freshshell.com

*To discover all the hidden Mac OS X settings you could ever think of, go to http://lri.me/osx.html#hidden-preferences*

**Zero Hosts File**
Template /etc/hosts file which stops porn, ads and other sites from functioning by pointing to localhost: http://someonewhocares.org/hosts/zero/

### Drupal

**Drush**  
Install the latest stable version of Drush using homebrew

    brew install drush

RVM

    curl -L https://get.rvm.io | bash -s stable --ruby

Append to .zshrc

    [[ -s "$HOME/.rvm/scripts/rvm" ]] && . "$HOME/.rvm/scripts/rvm"  # This loads RVM into a shell session


### Vagrant

Current setup at https://github.com/drupaldev-nginx  

**vagrant-vbplugin** Vagrant plugin which automatically installs the host's VirtualBox Guest Additions on the guest system  
````bash gem install vagrant-vbguest```` or [GitHub repo](https://github.com/dotless-de/vagrant-vbguest)

#### Puppet
Also look at http://puphpet.com

## Front-end tools

First check Ruby gems are up to date
    gem update --system

[**SASS**](http://sass-lang.com/)
    gem install sass

[**Compass**](http://compass-style.org/install/)
    gem install compass

[**Singularity**](http://singularity.gs/)
    gem install singularitygs

*Use [Bundler](http://bundler.io/) Gemfile to define your project's dependencies*
