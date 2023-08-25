## Create a simple “Hello, Wasm” C Program

## Prerequisite

- Docker Desktop 4.21.0
- Enable Wasm under Docker Desktop Settings 


<img width="757" alt="image" src="https://github.com/collabnix/wasmlabs/assets/34368930/065a8735-ab85-49a5-a42d-c0f5530fa24b">



## Installing WASI

WASI is a modular system interface for WebAssembly.

First, download wasi from the following URL:

```
wget https://github.com/WebAssembly/wasi-sdk/releases/download/wasi-sdk-16/wasi-sdk-16.0-macos.tar.gz
```

## Untar the WASI SDK

```
tar xvf wasi-sdk-16.0-macos.tar.gz
```


## Create the below file and save it as hello-world.c

```
 /* C program to print Hello Wasm! */
#include <stdio.h>
int main() {
   printf("Hello, Wasm!");
   return 0;
}
```

## Create a WASM module using WASI SDK

```
export WASI_SDK_PATH=`pwd`/wasi-sdk-16.0
CC="${WASI_SDK_PATH}/bin/clang"
$CC hello-world.c -o hello-world.wasm
```


## Verifying the file type

```
file hello-world.wasm 
hello-world.wasm: WebAssembly (wasm) binary module version 0x1 (MVP)
```

## Creating a Dockerfile

Here's a Dockerfile that you can use to containerize your "Hello, Wasm" C program:

```
FROM scratch
COPY --chmod=755 hello-world.wasm /hello-world.wasm
ENTRYPOINT [ "/hello-world.wasm" 
```


## Building the Image

```
docker build --platform=wasi/wasm --provenance=false -t hello-world-wasm --load .
```

## Running the container

```
docker run --platform=wasi/wasm --rm -i --runtime=io.containerd.wasmedge.v1 hello-world-wasm
```

<img width="1341" alt="image" src="https://github.com/collabnix/wasmlabs/assets/34368930/f44a9c49-79d6-43b0-bcd2-ac8932686732">



