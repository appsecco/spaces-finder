# Spaces finder

 #### Spaces finder is a tool to quickly enumerate [DigitalOcean Spaces](https://www.digitalocean.com/community/tutorials/an-introduction-to-digitalocean-spaces) to look for loot. It's similar to a subdomain bruteforcer but is made specifically for DigitalOcean Spaces and also has some extra features that allow you to grep for delicious files as well as download interesting files if you're not afraid to quickly fill up your hard drive.
 #### By [Bharath](https://twitter.com/0xbharath)
 #### Built on top of AWSBucketDump by [@ok_bye_now](https://twitter.com/ok_bye_now)

## Pre-Requisites
Non-Standard Python Libraries:

- [xmltodict](https://pypi.python.org/pypi/xmltodict)
- [requests](docs.python-requests.org/)
- Written in Python 3.6

## Overview

- This is a tool that enumerates DigitalOcean Spaces and looks for interesting files 
- I have example wordlists but I haven't put much time into refining them
- `https://github.com/danielmiessler/SecLists` will have all the word lists you need
- If you are targeting a specific company, you will likely want to use jhaddix's [enumall](https://github.com/jhaddix/domain) tool which leverages [recon-ng](https://bitbucket.org/LaNMaSteR53/recon-ng) and [Alt-DNS](https://github.com/infosec-au/altdns) 
- As far as word lists for grepping interesting files, that is completely up to you. The one I provided has some basics and yes, those word lists are based on files that I personally have found with this tool.
- Using the download feature might fill your hard drive up, you can provide a max file size for each download at the command line when you run the tool. Keep in mind that it is in bytes.


## Usage:

```
usage: python3 spaces_finder.py [-h] [-D] [-t THREADS] -l HOSTLIST [-g GREPWORDS] [-m MAXSIZE]

optional arguments:
  -h, --help    show this help message and exit`
  -D            Download files. This requires significant diskspace`
  -d            If set to 1 or True, create directories for each host w/ results`
  -t THREADS    number of threads`
  -l HOSTLIST`
  -g GREPWORDS  Provide a wordlist to grep for`
  -m MAXSIZE    Maximum file size to download.`
```

`python3 spaces_finder.py -l SpacesNames.txt -g interesting_keywords.txt -D -m 500000 -d 1 -t 5`
