# libreoffice

## Quick start / Deploy to LXC-SM
```
$> cd libreoffice
$libreoffice> lcp deploy --project=[ProjectName] --environment=[dev/uat/prd]
```

## Config Liferay side to use libre office
1. Control Panel -> CONFIGURATION:System Settings -> PLATFORM:Connectors
1. Turn [Server Enabled] on.
1. Change Server Host to ```libreoffice``` and save.

## Verify on Liferay side
Upload a a new word file to D&M, the preview will be created.

## Check libre office status on LXC-SM
After build & depoly, got project -> service -> libreoffice -> shell
https://console.liferay.cloud/projects/[projectname]-[dev]/services/libreoffice/shell

```
root@libreoffice-0:/# netstat -tuln
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State
tcp        0      0 0.0.0.0:8100            0.0.0.0:*               LISTEN
```

## Build and deploy to local

docker build on local.
```
docker build -t libreoffice .
```

docker start service on local.
```
docker run -it -m 8g -p 8100:8100 libreoffice
```

check service status:
```
$> nc -zv localhost 8100  
Connection to localhost port 8100 [tcp/xprint-server] succeeded!
```

