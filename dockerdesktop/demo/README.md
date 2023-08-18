
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
