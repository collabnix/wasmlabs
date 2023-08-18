Docker Desktop support the following Wasm runtime:

- Slight: Slight is a lightweight Wasm runtime that is designed to be fast and efficient. It is a good choice for running Wasm workloads that require high performance.
- Spin: Spin is a serverless Wasm runtime that is designed to be easy to use and deploy. It is a good choice for running Wasm workloads that are event-driven or that need to be scaled horizontally.
- WasmEdge: WasmEdge is a full-featured Wasm runtime that supports a wide range of features. It is a good choice for running Wasm workloads that require a high degree of flexibility and control.
- Wasmtime: Wasmtime is a Wasm runtime that is designed to be compatible with the WebAssembly specification. It is a good choice for running Wasm workloads that need to be portable to different environments.


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


  
