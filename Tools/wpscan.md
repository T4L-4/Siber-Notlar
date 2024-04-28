    WordPress Security Scanner

WPScan'i indirmek ve kurmak için:

    sudo apt install wpscan

WPScan'i güncellemek için:

    wpscan --update

## Usage:

Enumerating for Installed Plugins:

    wpscan --url http://wordpress.local --enumerate p

Enumerating for Installed Themes:

    wpscan --url http://cmnatics.playground/ --enumerate t 

Enumerating for Users:

    wpscan --url http://cmnatics.playground/ --enumerate u 

The "Vulnerable" Flag "v":

For plugins:

    wpscan --url http://cmnatics.playground/ --enumerate vp

For Themes:

    wpscan --url http://cmnatics.playground/ --enumerate vt

Performing a Password Attack:

    wpscan –-url http://cmnatics.playground –-passwords rockyou.txt –-usernames cmnatic

Adjusting WPScan's Aggressiveness (WAF):

    --plugins-detection aggressive

    --plugins-detection passive



---
[Tools](../tools.md) | [Ana Sayfa](../README.md)
