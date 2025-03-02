## Installing GO in certain way only to work it correctly. Local Hacking Way reference--  
```
sh
$ wget https://go.dev/dl/go1.24.0.linux-amd64.tar.gz
$ sudo tar -C /usr/local -xzf go1.24.0.linux-amd64.tar.gz
$ vim ~/.bashrc
export PATH=$PATH:/usr/local/go/bin
export GOPATH=$HOME/go
export GOBIN=$GOPATH/bin
export PATH=$PATH:$GOPATH/bin
$ source ~/.bashrc
$ sudo snap install helm --classic
$ curl -sSfL https://raw.githubusercontent.com/golangci/golangci-lint/HEAD/install.sh | sh -s -- -b $(go env GOPATH)/bin v1.64.5
$ golangci-lint --version
$ # Refer the link to work with SWL2, win11 docker desktop https://docs.docker.com/desktop/features/wsl/
$ [ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.27.0/kind-linux-amd64
$ # https://kind.sigs.k8s.io/docs/user/quick-start/
$ sudo apt-get install -y apt-transport-https ca-certificates curl gnupg
$ curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
$ ##Best way to install CF8-  https://github.com/cloudfoundry/cli/wiki/V8-CLI-Installation-Guide#installers-and-compressed-binaries
$ ## Helm https://helm.sh/docs/intro/install/
$ # https://carvel.dev/kbld/docs/develop/install/

sh
```

## Check ports before running the KIND for local testing. Ports like 80, 443 could already ne engaged. I check and changed it to 32080 and 32443 
```
sh
$ ss -tuln | grep :80 && ss -tuln | grep :443 
sh
```
# Ping and open website URL to see if you can reach the image hosted sites i.e. ghcr.io, docker.io etc. 
# Check if any proxy setup required 
