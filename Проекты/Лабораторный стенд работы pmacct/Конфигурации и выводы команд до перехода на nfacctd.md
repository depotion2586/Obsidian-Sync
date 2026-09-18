### ip addr
```
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute
       valid_lft forever preferred_lft forever
2: ens192: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:50:56:82:7b:6f brd ff:ff:ff:ff:ff:ff
    altname enp11s0
    inet 172.16.142.69/24 metric 100 brd 172.16.142.255 scope global dynamic ens192
       valid_lft 377445sec preferred_lft 377445sec
    inet6 fe80::250:56ff:fe82:7b6f/64 scope link
       valid_lft forever preferred_lft forever
6: veth-host@if5: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
    link/ether f2:ca:94:6e:a2:89 brd ff:ff:ff:ff:ff:ff link-netns Border
    inet 192.0.0.1/30 scope global veth-host
       valid_lft forever preferred_lft forever
    inet6 fe80::f0ca:94ff:fe6e:a289/64 scope link
       valid_lft forever preferred_lft forever
```

### Маршруты ip route
```
default via 172.16.142.1 dev ens192 proto dhcp src 172.16.142.69 metric 100
172.16.142.0/24 dev ens192 proto kernel scope link src 172.16.142.69 metric 100
172.16.142.1 dev ens192 proto dhcp scope link src 172.16.142.69 metric 100
172.17.15.1 via 172.16.142.1 dev ens192 proto dhcp src 172.16.142.69 metric 100
172.17.80.230 via 172.16.142.1 dev ens192 proto dhcp src 172.16.142.69 metric 100
172.17.81.70 via 172.16.142.1 dev ens192 proto dhcp src 172.16.142.69 metric 100
192.0.0.0/30 dev veth-host proto kernel scope link src 192.0.0.1
```

### Статус BGP сессий systemctl status bird
```
● bird.service - BIRD Internet Routing Daemon (IPv4)
     Loaded: loaded (/usr/lib/systemd/system/bird.service; enabled; preset: enabled)
     Active: active (running) since Sat 2026-09-12 18:15:29 +05; 6 days ago
   Main PID: 113308 (bird)
      Tasks: 1 (limit: 4460)
     Memory: 344.0K (peak: 1.5M)
        CPU: 54.391s
     CGroup: /system.slice/bird.service
             └─113308 /usr/sbin/bird -f -u bird -g bird

Sep 18 21:03:44 ustimenko bird[113308]: BGP: Unexpected connect from unknown address 127.0.0.1 (port 40625)
Sep 18 21:04:44 ustimenko bird[113308]: BGP: Unexpected connect from unknown address 127.0.0.1 (port 36785)
Sep 18 21:05:44 ustimenko bird[113308]: BGP: Unexpected connect from unknown address 127.0.0.1 (port 34805)
Sep 18 21:06:44 ustimenko bird[113308]: BGP: Unexpected connect from unknown address 127.0.0.1 (port 36523)
Sep 18 21:07:44 ustimenko bird[113308]: BGP: Unexpected connect from unknown address 127.0.0.1 (port 39335)
Sep 18 21:08:44 ustimenko bird[113308]: BGP: Unexpected connect from unknown address 127.0.0.1 (port 39119)
Sep 18 21:09:44 ustimenko bird[113308]: BGP: Unexpected connect from unknown address 127.0.0.1 (port 38273)
Sep 18 21:10:44 ustimenko bird[113308]: BGP: Unexpected connect from unknown address 127.0.0.1 (port 43953)
Sep 18 21:11:45 ustimenko bird[113308]: BGP: Unexpected connect from unknown address 127.0.0.1 (port 42603)
Sep 18 21:12:45 ustimenko bird[113308]: BGP: Unexpected connect from unknown address 127.0.0.1 (port 37253)
```
