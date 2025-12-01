# AOC25
[Advent of Code 2025](https://adventofcode.com/2025), in [InterSystems ObjectScript](https://docs.intersystems.com/irislatest/csp/docbook/DocBook.UI.Page.cls?KEY=PAGE_objectscript) 

My code will mostly compatible with other MUMPS implementation, because that's my background. You'll need to add and use your own functions to replace some the built-in Cache/IRIS specific ones (e.g. ZSTRIP, ZCVT/ZCONVERT and any ##class lazyness) if you're using something else.

I won't always do it on the day it was set for, some days I may skip because I get annoyed, or get distracted by real life! Eventually I'll give up updating this, it always happens. Time with my family is more important that solving a problem ... but sometimes I might come back to it... maybe I should commit those one day.

I use the InterSystems IRIS Community Edition (2025.2), deployed via Docker, with a [durable](https://docs.intersystems.com/irislatest/csp/docbook/DocBook.UI.Page.cls?KEY=AFL_containers#AFL_containers_durable) database directory. For my editor, I use Visual Studio Code with the [InterSystems ObjectScript](https://marketplace.visualstudio.com/items?itemName=intersystems-community.vscode-objectscript) extension pack.

## Docker Compose for my IRIS stack

```
version: '3.6'
services:
  iris:
    image: containers.intersystems.com/intersystems/iris-community:2025.2
    container_name: iris-new
    restart: unless-stopped
    ports:
      - 1972:1972
      - 52773:52773
      - 53773:53773
    environment:
      - ISC_DATA_DIRECTORY=/durable/IRIS
    volumes:
      - /opt/docker/iris/external:/external
      - /opt/docker/iris/durable:/durable
```
