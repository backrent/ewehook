# ewehook

Control eWelink devices over webhooks.

This solution addresses the integration of sonoff devices with Home Assistant.  These devices are cheap and readily available but require firmware flashing / brokers proving undesirable for some use cases.

## Features

* No setup required other than providing environment variables
* When eWelink devices are added or removed just delete and reinstall container

## Config

### Docker Run Command:

```docker run -d -p "9090:9000" -e "email=a@a.com" -e "pass=1234" -e "safehook=true" -e "ip=192.168.1.111" -e "port=9090" --name ewehook backrent/ewehook:latest```

### Environment Variables:
* email [required] - eWeLink login credential
* pass [required] - eWelinl login credential
* safehook [not required] - Add random digits to webhooks for increased security.  Webhooks are like passwords and should be kept secret.
* ip [not required] - Providing your host ip allows webhook commands to be transfered directly.
* port [not required] - Host port for convenience.

Check the log for webhook commands once the container is running.  Transfer command to new terminal and verify. That's it!

## FAQ
How do I view the log?

```docker logs ewehook```
