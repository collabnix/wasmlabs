Docker Desktop support the following Wasm runtime:

- WasmEdge
- slight from Deislabs
- wasmtime from Bytecode Alliance


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
