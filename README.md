# SMTP Relay with Rspamd & ClamAV
> **WARNING**: this project is not designed for production, but it's up to you whether to use in production or not :)

## Introduction
The goal of the project is to provide an automate way to deploy an SMTP Relay server with (antispam)[https://rspamd.com/] & (antivirus)[http://www.clamav.net/] solutions.


## How to use
1. Adjust the configuration `main.conf` to satisfy your needs:
2. If you're ready to get things up & working, run:
```
docker compose up -d 
```
3. Send e-mail to 172.22.0.1:25 or 172.22.0.1:587:
```
swaks --to user@test.local --from user@test.remote --server 172.22.0.1:25 --body "Hello World!"
swaks --to user@test.local --from user@test.remote --server 172.22.0.1:25 --attach - --suppress-data </path/to/eicar.zip
```

4. Let's go through logs in Rspamd Web-UI: (http://172.22.0.1:80)[http://172.22.0.1:80]


5. If you've played enough, stop the services:
```
docker compose down
```

## Why?

I'd been looking for a fast & easy way to present open-source antispam solution.  


## 3rd party packages
- (Postfix Relay)[https://hub.docker.com/r/freinet/postfix-relay]
- (Rspamd)[https://github.com/tiredofit/docker-rspamd]
- (ClamAV)[https://hub.docker.com/r/clamav/clamav]
- (Redis)[https://hub.docker.com/_/redis]

## License
MIT