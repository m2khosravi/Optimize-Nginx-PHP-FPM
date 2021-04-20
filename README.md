# Optimize-Nginx-PHP-FPM
Optimize Nginx + PHP-FPM for 5 million daily pageviews

We run a few high-volume websites which together generate around 5 million page views per day.  Every page on this sample just uses PHP but one of the times it happened to me it was on a PHP page that doesn't have any database calls which makes me think the issue is limited to NGINX, PHP-FPM or network settings.

We have 3 NGINX servers running behind a load balancer. Our database is separate on a cluster. I included our configuration files for nginx and php-fpm as well as our current RAM usage and PHP-FPM status. This is based on middle of the day (average traffic for us). 

Specs for each NGINX Server:
```bash
OS: CentOS 7
RAM: 128GB
CPU: 32 cores (2.4Ghz each)
Drives: 2xSSD on RAID 1
RAM Usage (free -g)
```

```bash       
        total        used        free      shared  buff/cache   available
Mem:            125          15          10           3         100         103
```
PHP-FPM status (Status/Node1)
```bash
pool:                 www
process manager:      dynamic
start time:           03/Mar/2016:03:42:49 -0800
start since:          1171262
accepted conn:        69827961
listen queue:         0
max listen queue:     0
listen queue len:     0
idle processes:       1670
active processes:     1
total processes:      1671
max active processes: 440
max children reached: 0
slow requests:        0
```
