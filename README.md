# macos-compiled-fontforge
A built dump of a working fontforge/ttfautohint brew install that works with grunt-webfont

Fontforge has problems working with grunt-webfont on some systems due to incompatible newer versions in the brew repository. This is a working compiled set of brew Cellar folders which can be copied into your brew folder. These versions were compiled on Mac OS X mavericks on an intel iMac.

To install:
* Checkout this repo:

  ```
  git clone git@github.com:grahamgilchrist/macos-compiled-fontforge.git
  ```
  
* Install fontforge and ttfauthint via brew to establish folders in the brew cellar:
   
   ```
   brew install fontforge ttfautohint
   ```
   
* Move the folders from this repo over the installed versions:

   ```
   rm -rf $(brew --prefix)/Cellar/fontforge
   rm -rf $(brew --prefix)/Cellar/ttfautohint
   mv macos-compiled-fontforge/fontforge $(brew --prefix)/Cellar/fontforge
   mv macos-compiled-fontforge/ttfautohint $(brew --prefix)/Cellar/ttfautohint
  ```
* Re-establish the symlinks via brew:

  ```
   brew link ttfautohint fontforge
  ```
  
* Check the install is working:

  ```
  brew info ttfautohint fontforge
  ```
  
    * ttfautohint should list:
        *  `ttfautohint: stable 1.3 (bottled), HEAD`
        *  `/usr/local/Cellar/ttfautohint/0.97 (8 files, 172K)`
    * fontforge should list:
        *  `fontforge: stable 20150430 (bottled)`
        *  `/usr/local/Cellar/fontforge/20120731 (365 files, 12M) *`
