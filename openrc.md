openrc init
---

#### add service

```
rc-update add [service] runlevel
```

#### start service

```
rc-service service_name start
```

or

```
/etc/init.d/service_name start
```

#### list service

```
rc-status -a
```

or

```
ls /etc/init.d
```
