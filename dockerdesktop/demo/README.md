
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

