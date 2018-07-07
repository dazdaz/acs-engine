## Configure acs-engine
```
mkdir $HOME/gopath
# Add to $HOME/.profile
cat >> $HOME/.profile <<_EOF_
export PATH=$PATH:/usr/local/go/bin
export GOPATH=$HOME/gopath
_EOF_
source $HOME/.profile
go get github.com/Azure/acs-engine
go get all
cd $GOPATH/src/github.com/Azure/acs-engine
go build
./acs-engine

acs-engine upgrade --deployment-dir _output/edsk8s02/ --location northcentralus --resource-group K8s03 --subscription-id --upgrade-version 1.8.4 --auth-method client_secret --client-id --client-secret 

```
* https://github.com/Azure/acs-engine/blob/master/docs/acsengine.md
