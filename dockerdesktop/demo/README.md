
## Demonstrating Hello World using WasmEdge Runtime


```
docker run \
  --runtime=io.containerd.wasmedge.v1 \
  --platform=wasi/wasm \
  secondstate/rust-example-hello
```


## Demonstrating Hello World using Wasmtime Runtime

```
docker run \
  --runtime=io.containerd.wasmtime.v1 \
  --platform=wasi/wasm \
  secondstate/rust-example-hello
Hello WasmEdge!
```


##  Running a Wasm application with Docker Compose


The same application can be run using the following Docker Compose file:


```
services:
  app:
    image: secondstate/rust-example-hello
    platform: wasi/wasm
    runtime: io.containerd.wasmedge.v1
````

## Start the application using the normal Docker Compose commands:

```
 docker compose up
```


## Running Wasm and amd64 containers side by side

```
git clone https://github.com/second-state/microservice-rust-mysql.git
```

## Bringing up the services

```
cd microservice-rust-mysql
docker compose up
```

## Checking the architecture

```
docker image inspect demo-microservice | grep -A 3 "Architecture"
        "Architecture": "wasm",
        "Os": "wasi",
        "Size": 3397469,
        "VirtualSize": 3397469,
```
