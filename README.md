# macos-compiled-fontforge
A built dump of a working fontforge/ttfautohint brew install that works with grunt-webfont

Fontforge has problems working with grunt-webfont on some systems due to incompatible newer versions in the brew repository. This is a working compiled set of brew Cellar folders which can be copied into your brew folder. These versions were compiled on Mac OS X mavericks on an intel iMac.

To install:
* checkout this repo `git clone repo-url macos-compiled-fontforge`
* Install fontforge and ttfauthint via brew to establish folders in the brew Cellar
    * `brew install fontforge ttfautohint`
* Move the folders from this repo over the installed versions
    * `rm -rf /usr/local/Cellar/fontforge`  
    * `rm -rf /usr/local/Cellar/ttfautohint`  
    * `mv macos-compiled-fontforge/fontforge /usr/local/Cellar/fontforge`
    * `mv macos-compiled-fontforge/ttfautohint /usr/local/Cellar/ttfautohint`
* Re-establish the symlinks via brew
    * `brew link ttfautohint fontforge`
* Check the install is working
    * `brew info ttfautohint fontforge`
    * ttfautohint should list:
        *  `ttfautohint: stable 1.3 (bottled), HEAD`
        *  `/usr/local/Cellar/ttfautohint/0.97 (8 files, 172K)`
    * fontforge should list:
        *  `fontforge: stable 20141230 (bottled)`
        *  `/usr/local/Cellar/fontforge/20120731 (365 files, 12M) *`
