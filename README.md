# en_DE: English language locale for Germany

I created this file by merging the locale files [en_US](https://sourceware.org/git/?p=glibc.git;a=blob;f=localedata/locales/en_US) and [de_DE](https://sourceware.org/git/?p=glibc.git;a=blob;f=localedata/locales/de_DE) as suggested [here](https://unix.stackexchange.com/a/209887) so you don't need to. Feel free to follow [this post](https://askubuntu.com/a/162714) to modify it further.

All European/German formats are kept (with exception of exchanging decimal point and thousands separator, i.e. "," and "."), only language-related settings are translated (e.g. months and week days).

## Installation
1. Download the locale file as well as the [UTF-8 charmap](https://sourceware.org/git/?p=glibc.git;a=blob;f=localedata/charmaps/UTF-8).
2. Go to the directory where the files are located and run the command `sudo localedef -i en_DE -f UTF-8 en_DE.UTF-8 -c -v` to define the locale `en_DE.UTF-8` in the output path. `-c` forces creation despite of warnings or errors and `-v` lets you see them, check `localedef -?` for more info.
3. Copy the downloaded locale file to the locales directory by running `sudo cp en_DE /usr/share/i18n/locales`.
4. Add the locale as an option to `/etc/locale.gen` (uncommented of course).
5. Run `sudo locale-gen` to generate all the locales specified in the above file.
6. Tell your system to use the locale, either by choosing it in System Settings or using `sudo update-locale LANG="en_DE.UTF-8` which changes the `/etc/default/locale` file. For other options see [this tutorial](https://www.tecmint.com/set-system-locales-in-linux/)

## Notes
If these steps do not suffice, try following advice in the two before-mentioned posts [here](https://unix.stackexchange.com/a/209887) and [here](https://askubuntu.com/a/162714).

The above steps only change the locale, not the system language itself. You can change the language by running `sudo update-locale LANGUAGE="en_US"`. This can however be overwritten by your system settings

## Disclaimer
I take no responsibility for any damage caused to your system. Tested on Debian 11.
