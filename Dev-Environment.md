
**Xcode**  
Install via Mac App Store, run once to Agree to License.  
Let everyone know where Xcode is:

    sudo xcode-select -switch /Applications/Xcode.app/Contents/Developer

**Homebrew**  
Package manager http://brew.sh

    ruby <(curl -fsSkL raw.github.com/mxcl/homebrew/go)

**Zsh &amp; Oh-My-Zsh**

    brew install zsh
    curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh

**Git**  
Let's just use homebrew to install it.

    brew install git
    # global settings
    git config --global user.name "Tom Bamford"
    git config --global user.email "tom@halfmesh.com"
    
    # To save typing your password everytime, see https://help.github.com/articles/set-up-git
    # Set git to use the osxkeychain credential helper
    git config --global credential.helper osxkeychain
    
    # check for SSH key, if not create one
    [[ -f ~/.ssh/id_rsa.pub ]] || ssh-keygen -t rsa -C "tom@halfmesh.com"
    # remember to use a passphrase, otherwise you run the risk of leaving passphraseless keys on servers.
    [[ -f ~/.ssh/id_rsa.pub ]] && cat ~/.ssh/id_rsa.pub | pbcopy
    # add your SSH keys to github https://github.com/account/ssh
    
If you are the type that doesn't like entering their passphrase all the time, have a look at SSH agent forwarding https://help.github.com/articles/using-ssh-agent-forwarding.
    
   
If you're not using the dotfiles below, remember to add .DS_Store to your global .gitignore file.


**Dotfiles**  
If you haven't already got your own dotfiles repository, then go to [dotfiles.github.io](http://dotfiles.github.io) and behold the magic

**Fresh**  
Keeps your dot files fresh http://freshshell.com


*To discover all the hidden Mac OS X settings you could ever think of, go to http://lri.me/osx.html#hidden-preferences*
