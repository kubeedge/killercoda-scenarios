## Clone the repository

```
git clone https://github.com/kubeedge/examples.git
```
Change the directory to apache-beam-analysis

```
cd examples/apache-beam-analysis
```

### Add following vendor packages:

```
go get -u github.com/yosssi/gmq/mqtt
go get -u github.com/yosssi/gmq/mqtt/client
```

run:
```
go build testmachine.go
./testmachine
```