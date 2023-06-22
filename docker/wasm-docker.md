## How does Wasm work with Docker?

Docker Desktop now includes support for WebAssembly. It is implemented with a containerd shim that can run Wasm applications using a Wasm runtime called WasmEdge. This means that instead of the typical Windows or Linux containers which would run a separate process from a binary in the container image, you can now run a Wasm application in the WasmEdge runtime, mimicking a container.

As a result, the container image does not need to contain OS or runtime context for the running application - a single Wasm binary suffices.

This is explained in detail in Docker's Wasm technical preview article.

## How does the Wasm integration actually work?

- Docker collaborated with WasmEdge to create a containerd shim.
- This shim extracts the Wasm module from the OCI artifact and runs it using the WasmEdge runtime.
- Docker added support to declare the Wasm runtime, which will enable the use of this new shim.


![image](https://github.com/collabnix/wasmlabs/assets/313480/27e96b9d-bd76-4a59-97a3-5e1b22afb3d0)

## Why Docker?

At Docker, our goal is to help developers bring their ideas to life by conquering the complexity of app development. We strive to make it easy to build, share, and run your application, regardless of the underlying technologies. By making containers accessible to all, we proved our ability to make the lives of developers easier and were recognized as the #1 most-loved developer tool.

We see Wasm as a complementary technology to Linux containers where developers can choose which technology they use (or both!) depending on the use case. And as the community explores what’s possible with Wasm, we want to help make Wasm applications easier to develop, build, and run using the experience and tools you know and love.
