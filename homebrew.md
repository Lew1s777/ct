# homebrew #

installation
---
dependencies
```
glibc gcc
```
installation
```
#install(GNU/Linux)
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh
#add to $path
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> ~/.bash_profile
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

basic gramma
---
install package
```
brew install <formula>
```

search package
```
brew search <formula>
```

fetch info about a package
```
brew info <formula>
```

list package
```
brew list
```

remove package
```
brew uninstall <formula>
```

update package
```
brew upgrade <formula>            #update a particular package
brew update
```
