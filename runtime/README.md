Docker Desktop support the following Wasm runtime:

- WasmEdge
- slight from Deislabs
- wasmtime from Bytecode Alliance
- Spin


All of these runtimes uses the runwasi library.


## WasmEdge

WasmEdge is a High-Performance WebAssembly Runtime that:

- Is Open Source, part of the CNCF.
- Supports all major CPU architectures (x86, ARM, RISC-V).
- Supports all major Operating Systems (Linux, Windows, macOS) as well as others such as seL4 RTOS, Android.
- Is Optimized for cloud-native and Edge applications.
- Is Extensible and supports standards and emerging technologies
- AI Inference with Tensorflow, OpenVINO, PyTorch
- Async networking with Tokio. Supports microservices, database clients, message queues, etc.
- Integrates seamlessly with containers ecosystem, Docker and Kubernetes (as shown in this article!)

## Resources:

- [WebAssembly: Docker without containers!](https://wasmlabs.dev/articles/docker-without-containers/)

## Spin

- Spin is a framework for building and running event-driven microservice applications with WebAssembly (Wasm) components.
- Spin uses Wasm because it is sandboxed, portable, and fast. Millisecond cold start times mean no need to keep applications “warm”.
- Many languages have Wasm implementations, so developers don’t have to learn new languages or libraries.
- Spin is open source and built on standards, meaning you can take your Spin applications anywhere.
- There are Spin implementations for local development, for self-hosted servers, for Kubernetes, and for cloud-hosted services.


## Resources

- [Docker Desktop and Spin for Serverless WebAssembly Apps](https://www.fermyon.com/blog/spin-in-docker)


  
