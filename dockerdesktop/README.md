## Getting Started with Wasm on Docker Desktop

## Install Docker Desktop

- [Download Docker Desktop](https://www.docker.com/products/docker-desktop/) from this link and install it on your Macbook.


## Enable Containerd

Enable Experimental Feature that Allows Docker to Run Wasm Containers

<img width="1229" alt="image" src="https://github.com/collabnix/wasmlabs/assets/313480/e7d6fcf3-594a-4759-a220-6744fb53a60f">


## Create a simple “Hello, Wasm” C Program

Create the below file and save it as hello-world.c

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
# Use a base image with the necessary toolchain for building the WASM module
FROM emscripten/emsdk 

# Set the working directory inside the container
WORKDIR /app

# Copy the C source file into the container
COPY hello-world.c .

# Compile the C program into a WebAssembly module
RUN emcc hello-world.c -o hello-world.wasm

# Set the command to run when the container starts
CMD ["echo", "Docker container is running!"]

# Optionally, you can uncomment the following line if you want to execute the WebAssembly module
# CMD ["emrun", "--no_browser", "--port", "8080", "."]
```

Here's a breakdown of the Dockerfile:

- The base image emscripten/emsdk  includes the necessary Emscripten toolchain for building WebAssembly modules.
- The working directory inside the container is set to /app.
- The hello-world.c file is copied into the container's /app directory.
- The emcc command is used to compile the C program into a WebAssembly module named hello-world.wasm.
- The CMD instruction sets the default command to run when the container starts. In this example, it simply echoes a message, but you can modify it as needed.
- Optionally, you can uncomment the last CMD line if you want to execute the WebAssembly module using Emscripten's emrun tool.


## Building the Image

```
docker buildx build . --file=Dockerfile --tag=ajeetraina/hello-wasm-docker
```

## Running the container

```
docker run  --platform=wasi/wasm32 ajeetraina/hellowasm
Docker container is running!
```
