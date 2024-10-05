# bashdep

A minimalistic and straightforward **bash dependency manager**.

---

### Usage

Usage example from
[Chemaclass/bash-skeleton](https://github.com/Chemaclass/bash-skeleton/blob/main/install-dependencies.sh)

```bash
#!/bin/bash
# Make sure the dependency manager is installed
if [ ! -f lib/bashdep ]; then
  [[ ! -d "lib" ]] && mkdir -p "lib"
  curl -s -L -o lib/bashdep \
    https://github.com/Chemaclass/bashdep/releases/download/0.1/bashdep
  chmod +x lib/bashdep
fi

DEPENDENCIES=(
  "https://github.com/TypedDevs/bashunit/releases/download/0.17.0/bashunit"
  "https://github.com/Chemaclass/create-pr/releases/download/0.6/create-pr"
  "https://github.com/Chemaclass/bash-dumper/releases/download/0.1/dumper.sh@dev"
)

source lib/bashdep
bashdep::setup dir="lib" dev-dir="src/dev" silent=false
bashdep::install "${DEPENDENCIES[@]}"
```

#### Output

```bash
Downloading 'bashunit' to 'lib'...
> bashunit installed successfully in 'lib'
Downloading 'create-pr' to 'lib'...
> create-pr installed successfully in 'lib'
Downloading 'dumper.sh' to 'src/dev'...
> dumper.sh installed successfully in 'src/dev'
```
