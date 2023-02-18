# 🌐 DDNS

[![License](https://img.shields.io/badge/License-BSD_3--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
[![Release](https://img.shields.io/badge/Calver-YY.WW.REVISION-22bfda.svg)](https://calver.org/)
[![Linters](https://github.com/Plaenkler/DDNS/actions/workflows/linters.yml/badge.svg)](https://github.com/Plaenkler/DDNS/actions/workflows/linters.yml)
[![Support me](https://img.shields.io/badge/Support%20me%20%E2%98%95-orange.svg)](https://www.buymeacoffee.com/Plaenkler)

DDNS provides a straightforward way to update dynamic DNS entries without fiddling around in the command-line or a file. The easy to use interface allows for uncomplicated setup and management.

> **Note:** If your DynDNS provider is not listed open an issue and I will integrate it.

<table>
  <tr>
    <td><img src="https://user-images.githubusercontent.com/60503970/219900612-b4d7d3c4-7e0a-4dca-bc73-63c4822c5133.png" width="480"/></td>
    <td><img src="https://user-images.githubusercontent.com/60503970/219900611-dfaa9c4b-13ac-4fc4-b7ca-1cdae47961a9.png" width="480"/></td>
  </tr>
</table>

## 🎯 Project goals

- [x] Scheduled update service
- [x] Database for DDNS Jobs
- [x] Consistent configuration
- [x] Simple & User friendly UI
- [x] Deploy as Docker Container
- [ ] Deploy as Windows Service
- [ ] Secure authentication
- [ ] Additional support for IPv6

## 🏷️ Supported providers

`Strato` `DDNSS`

## 📜 Installation guide

### Deploy with Docker

It is recommended to use [docker-compose](https://docs.docker.com/compose/) as it is very convenient. The following example shows a simple deployment without a proxy.

```yaml
version: '3.9'

services:
  ddns:
    image: plaenkler/ddns:latest
    container_name: ddns
    restart: unless-stopped
    ports:
      - 80:80
    volumes:
      - ./ddns:/app/data
```

### Build from source

From the root of the source tree, run:

```text
go build -o ddns.exe cmd/main.go
```

> Make sure that CGO is operational!

### Configuration

At the first start the program creates a config file. The settings can be adjusted both in the user interface and in the file. By default, the following values are set:

```yaml
Port: 80
Interval: 600
```
