## SonarSearch
This repository contains all the code needed to create index Rapid7's Project Sonar Forward DNS lookup datasets into a MongoDB database, and query them in a time efficient fashion. 

An instance of this API (Crobat) is online at the following URL: 

> https://sonar.omnisint.io

### Crobat API

Currently, the Crobat API implements three endpoints. 

``` normal
/subdomains/{domain} - All subdomains for a given domain
/tlds/{domain} - All tlds found for a given domain
/all/{domain} - All results accross all tlds for a given domain
```

No authentication is required to use the API, nor special headers, so go nuts. 

However, the API does have pagination. Currently pages are limited to 10k results per page. To request pages, add `?page=X` to the request, where `X` is the page number. Crobat automatically handles pagination, so no need to worry about this if you are using the client.

### Crobat
Crobat is a command line utility designed to allow easy querying of the Crobat API. To install the client, run the following command: 
``` normal
$ go get github.com/cgboal/sonarsearch/crobat
```

By default, Crobat will return a list of result in plain-text, however, JSON output is also supported. 

Below is a full list of command line flags:
``` normal
$ crobat -h
Usage of crobat:
  -r string
        Perform reverse lookup on IP address or CIDR range
  -s string
        Get subdomains for this value
  -t string
        Get tlds for this value
```     

### Third-Party SDKs

* [Crystal SDK and CLI tool complete with Docker images](https://github.com/PercussiveElbow/crobat-sdk-crystal) made by [@mil0sec](https://twitter.com/mil0sec)

### Contributing 
If you wish to contribute a SDK written in other languages, shoot me a DM on Twitter (@CalumBoal), or open an issue on this repository and I will provide a link to your repository in the Third-Party SDK's section of this readme. 
