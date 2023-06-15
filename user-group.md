Users & groups
===
also see aur/```adduser```

useradd
---
usage:
```
useradd [argument] [username]
```

argument:
- ```-m``` create home directory
- ```--system``` system user
- ```-s /usr/bin/nologin``` disable shell access
- ```-u [number]``` specific user id
- ```-g [number]``` specific group id

examples

- add a normal user with home directory
```
useradd -m archie
```

- add a system user
```
useradd --system -s /usr/bin/nologin username
```

usermod
---
- change one's home directory
```
usermod -d /my/new/home -m username
```

- change one's name
```
usermod -l newname oldname
```

-add a user to additional groups
```
usermod -aG [additional_groups] [username]
```

groupadd
---
usage:
```
groupadd [groupname]
```

