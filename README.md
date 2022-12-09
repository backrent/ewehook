# ewehook

Control eWelink devices over webhooks.

This solution addresses the integration of sonoff devices with Home Assistant.  These devices are cheap and readily available but require firmware flashing and mqtt brokers proving undesirable in my use case.

## Features

* No setup required other than providing environment variables
* When eWelink devices are added or removed just delete and reinstall container

## Config

```docker run -d -p "9090:9000" -e "email=a@a.com" -e "pass=1234" -e "safehook=true" -e "ip=192.168.1.111" -e "port=9090" --name ewehook backrent/ewehook:latest```

* email [required] - eWeLink login credential
* pass [required] - eWelinl login credential
* safehook [not required] - Add random digits to webhooks for increased security.  Webhooks are like passwords and should be kept secret.
* ip [not required] - Providing your host ip allows webhook commands to be copy and pasted directly.
* port [not required] - Host port for convenience.

Check the log for webhook commands once the container is running.  Transfer command to new terminal and verify. That's it!

To view the log file:
```docker logs ewehook```
