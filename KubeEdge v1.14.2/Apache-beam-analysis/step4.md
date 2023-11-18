## Clone the repository

```
git clone https://github.com/kubeedge/examples.git
```{{execute}} 
Change the directory to apache-beam-analysis

```
cd examples/apache-beam-analysis
```{{execute}} 

### Add following vendor packages:

```
go get -u github.com/yosssi/gmq/mqtt
go get -u github.com/yosssi/gmq/mqtt/client
```{{execute}} 

run:
```
go build testmachine.go
./testmachine
```{{execute}} 