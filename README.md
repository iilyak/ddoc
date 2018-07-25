# ddoc

Helper alfred script for passing git credentials to docker container

# Installation

1. Install [alfred](https://github.com/kcmerrill/alfred).
   You can build it in docker as follows:

   ```
   docker run --rm -it -v "$PWD":/usr/src/app \
     -w /usr/src/app \
     -e GOPATH=/usr/src/app/build \
     -e GOOS=darwin -e GOARCH=amd64 \
     golang go get github.com/kcmerrill/alfred
   cp build/bin/darwin_amd64/alfred ~/bin/
   ```

2. Run setup withard
   ```
   cd <to the directory with Dockerfile>
   alfred iilyak/ddoc:setup
   ```
3. Build development image
   ```
   alfred build ddock.20.3.6
   ```

# Usage

1. Start container
   ```
   alfred iilyak/ddoc:start ddock.20.3.6
   ```
2. Add ssh key to ssh-agent inside docker container
   ```
   ssh-add ~/.ssh/id_rsa
   ```
