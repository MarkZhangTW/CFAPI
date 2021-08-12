# CFAPI
Simple API for CloudFlare.

It's working with `nmcli` now if you want to update IP of a DNS record.

## Dependencies
- [curl](https://curl.se/)
- [jq](https://stedolan.github.io/jq/)

## Installation
Get main script from this repo.
```bash
# 1. Get main script from this repo.
git clone --depth 1 https://github.com/markzhang1996/CFAPI.git
# 2. Make .CFAPI/main executable.
chmod u+x ./CFAPI/main
```

## Configuration
Create file `config` in `CFAPI`.
- domain: mandatory
    - Your DNS domain name
- zoneID: mandatory
    - Domain's zone ID (get from bottom right corner of DNS page)
- token: mandatory
    - Your API token (create from your profile page)
- interface: optional
    - Script will get IP from this interface.
```bash
domain=mydomain.example
zoneID=myZoneID
token=myAPIToken
interface=eth0
```

## Usage
- Get all records info.
```bash
CFAPI/main get
```
- Get a record info.
    - The record must be created on CloudFlare web.
```bash
CFAPI/main get mySubdomain
```
- Update IP of a subdomain
    - The record must be created on CloudFlare web.
```bash
CFAPI/main put mySubdomain
```