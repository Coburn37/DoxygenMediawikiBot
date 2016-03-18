# DoxyMWbot

A python bot using PyWikibot and Doxygen to put Doxygen docs onto a MediaWiki wiki
Licensed under the MIT License (should be included with the source code in LICENSE.txt)


### SETUP:

1. Consider setting up a virtual environment for your project installation
1. Install the required Python modules through pip or however (`setup.bat` originally did this but it's out of date)
 1. PyWikibot (https://github.com/wikimedia/pywikibot-core)
 2. BeautifulSoup4 (http://www.crummy.com/software/BeautifulSoup/)
2. Create the family for your PyWikibot as described in their documentation (https://www.mediawiki.org/wiki/Manual:Pywikibot/Use_on_third-party_wikis)
3. Configure your options in the `config` dictionary in `doxymwglobal.py`

### USAGE:

```
USAGE: python doxymw.py <command> [<opts>]

<command> can be:
  update   update some wiki with documentation
  cleanup  delete all the autogenerated documentation on a wiki

<opts> can be:
  -i,   --interactive   Interactive mode
  -d:_, --debug:_       Debug where _ is in [doxygen]
  -p:_, --printLevel:_  Show msgs with severity _ in [error, warning, info, or debug]
  -w,   --warnIsError   If warnings cause program to stop
  -h,   --help          Prints help message
```

### FAQ:

#### Why do some page names have '!' characters in them?

Page titles in MediaWiki are not allowed to contain a few characters for example '<', '>', and '?'.
To compensate for this all invalid characters are changed to '!'s and '_'s to ' ' by MediaWiki default
MediaWiki's `{{DISPLAYTITLE:_}}` magic word is also used when available to show the correct page title on the page (but the actual page link and title in the database will contain '!'s)

#### Find a bug? Encounter an error?

Send me a message on GitHub or somewhere
