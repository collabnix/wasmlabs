## Wasm and Rust



## Getting Started


```
mkdir wasm
cd wasm
```

## Add Wasm32-wasi to yoru Rust Toolchain


The command ```rustup target add wasm32-wasi``` adds the wasm32-wasi target to your Rust toolchain. This target allows you to compile Rust code to WebAssembly (WASM) for the WebAssembly System Interface (WASI).

```
rustup target add wasm32-wasi
```

## Verify if  Rust is configured and you’re ready to create the app.

```
rustup target list
```

```
....
aarch64-apple-darwin (installed)
...
wasm32-unknown-emscripten
wasm32-unknown-unknown (installed)
wasm32-wasi (installed)
...
```

## Scaffold up a simple Rust app

```
cargo new hello-docker
     Created binary (application) `hello-docker` package
```

## Display the main.rs file

```
wasm-rust % cat hello-docker/src/main.rs
fn main() {
    println!("Hello, world!");
}
```

## Compile the app into a Wasm binary

```
cd hello-docker
cargo build --target wasm32-wasi --release
 ```
 
 Results:
 
 ```
    Compiling hello-docker v0.1.0 (/Users/ajeetsraina/June/wasm-rust/hello-docker)
    Finished release [optimized] target(s) in 0.91s
 ```
 
 The command outputs the compiled hello-docker.wasm Wasm binary into the hello-docker/target/wasm32-wasi/release folder.
 
 ## Build a Wasm app into an OCI image
 
 ```
 FROM scratch
COPY ./target/wasm32-wasi/release/hello-docker.wasm /hello-docker.wasm
ENTRYPOINT [ "hello-docker.wasm" ]
```

## Building the Wasm Docker Image

```
docker buildx build  -t docker-wasm:0.1 .
```

```
[+] Building 0.1s (5/5) FINISHED
 => [internal] load .dockerignore                                                                                                        0.0s
 => => transferring context: 2B                                                                                                          0.0s
 => [internal] load build definition from Dockerfile                                                                                     0.0s
 => => transferring dockerfile: 193B                                                                                                     0.0s
 => [internal] load build context                                                                                                        0.0s
 => => transferring context: 555B                                                                                                        0.0s
 => CACHED [1/1] COPY ./target/wasm32-wasi/release/hello-docker.wasm /hello-docker.wasm                                                  0.0s
 => exporting to image                                                                                                                   0.0s
 => => exporting layers                                                                                                                  0.0s
 => => exporting manifest sha256:9dd634d839696064bd7d271e2a9e29b253966dd33cba872bcfa0734d42596bba                                        0.0s
 => => exporting config sha256:b6363537ce1cb5f397262cc2033c8a552d29eee6636d6e68e51f4ab56022175d                                          0.0s
 => => exporting attestation manifest sha256:ee8e72989fe4ed5a3cfe01ef0732423baecda114e4871a87509b168e6e221a75                            0.0s
 => => exporting manifest list sha256:bb13d3cc4863d461cd8fdad560c11dab8d1f60d6c3a97474b1eac68ea3af65b3                                   0.0s
 => => naming to docker.io/library/docker-wasm:0.1                                                                                       0.0s
 => => unpacking to docker.io/library/docker-wasm:0.1
 ```
 
 
