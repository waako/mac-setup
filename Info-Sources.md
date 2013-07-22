# Categorised list of reading for setting up Mac environment

## Sublime Text

### Must have

**Package Control** http://wbond.net/sublime_packages/package_control/installation#ST3  
*Please note, the Packages/ folder listed below refers to the folder that opens when you use the Preferences > Browse Packages… menu.*  

    cd Packages/
	git clone https://github.com/wbond/sublime_package_control.git "Package Control"
	cd "Package Control"
	git checkout python3


### Packages

[**Github flavor Markdown**](https://github.com/revolunet/sublimetext-markdown-preview) 
[**Advanced New File**](https://github.com/skuroda/Sublime-AdvancedNewFile) 
[**CheckBounce**](https://github.com/phyllisstein/CheckBounce) *Spellcheck* 
[**Code Formatter**](https://github.com/akalongman/sublimetext-codeformatter) 
[**SideBarEnhancements**](https://github.com/titoBouzout/SideBarEnhancements) 
[**GotoRecent**](https://github.com/paccator/GotoRecent) 
[**Gist**](https://github.com/condemil/Gist) 
[**ALL Autocomplete**](https://github.com/alienhard/SublimeAllAutocomplete) 
[**Emmet**](http://docs.emmet.io/) 
[**SublimeLinter**](http://github.com/Kronuz/SublimeLinter) 
[**HTML5**](https://github.com/mrmartineau/HTML5) 
[**SCSS](https://github.com/kuroir/SCSS.tmbundle/tree/SublimeText2) 
[**ColorHighlighter**](https://github.com/Monnoroch/ColorHighlighter) 
[**CSS Comb**](http://csscomb.com/)


### Extras

**Icon replacement** https://github.com/dmatarazzo/Sublime-Text-2-Icon 
**Mardown Preview** https://github.com/revolunet/sublimetext-markdown-preview 
**Web Inspector** http://sokolovstas.github.io/SublimeWebInspector/ 
**Source Code Pro font** http://blogs.adobe.com/cantrell/archives/2012/10/using-source-code-pro-with-sublime-text-2.html 
**Puppet** https://github.com/alister/puppet-sublimetext2 




## Browser Testing

**IE VMs** http://www.modern.ie/en-us/virtualization-tools#downloads
    #!/bin/sh
    #
    # Downloads all IE VMs simultaneously

    wget https://az412801.vo.msecnd.net/vhd/IEKitV1_Final/VirtualBox/OSX/IE6_WinXP.ova.zip & curl -O "https://az412801.vo.msecnd.net/vhd/IEKitV1_Final/VirtualBox/OSX/IE8_XP/IE8.XP.For.MacVirtualBox.ova" & curl -O "https://az412801.vo.msecnd.net/vhd/IEKitV1_Final/VirtualBox/OSX/IE7_Vista/IE7.Vista.For.MacVirtualBox.part{1.sfx,2.rar,3.rar,4.rar,5.rar}" & curl -O "https://az412801.vo.msecnd.net/vhd/IEKitV1_Final/VirtualBox/OSX/IE8_Win7/IE8.Win7.For.MacVirtualBox.part{1.sfx,2.rar,3.rar,4.rar,5.rar,6.rar}" & curl -O "https://az412801.vo.msecnd.net/vhd/IEKitV1_Final/VirtualBox/OSX/IE9_Win7/IE9.Win7.For.MacVirtualBox.part{1.sfx,2.rar,3.rar,4.rar,5.rar}" & curl -O "https://az412801.vo.msecnd.net/vhd/IEKitV1_Final/VirtualBox/OSX/IE10_Win7/IE10.Win7.For.MacVirtualBox.part{1.sfx,2.rar,3.rar,4.rar}" & curl -O "https://az412801.vo.msecnd.net/vhd/IEKitV1_Final/VirtualBox/OSX/IE10_Win8/IE10.Win8.For.MacVirtualBox.part{1.sfx,2.rar,3.rar}"