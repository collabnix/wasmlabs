# List of Companies and Organizations Using Wasm

This list was refreshed by scanning public GitHub repositories and keeping only entries with clear GitHub evidence.

| S. No | Name | How are they using it? | GitHub evidence |
|-----------|-------------|--------------|--------------|
| 1 | Cloudflare | Cloudflare built `workerd`, the JavaScript and Wasm runtime that powers Cloudflare Workers, and also ships Wasm-based tools such as `html-rewriter-wasm`. | [workerd](https://github.com/cloudflare/workerd)<br>[html-rewriter-wasm](https://github.com/cloudflare/html-rewriter-wasm) |
| 2 | Fastly | Fastly Compute runs application code compiled to Wasm and WASI for edge workloads, with official SDKs and starter projects for developers. | [compute-sdk-go](https://github.com/fastly/compute-sdk-go) |
| 3 | Shopify | Shopify Functions uses Wasm modules to run merchant extensions such as custom commerce logic, with an official Wasm API repository. | [shopify-function-wasm-api](https://github.com/Shopify/shopify-function-wasm-api) |
| 4 | Microsoft | Microsoft maintains Wasm-based developer tooling such as `wassette` and `vscode-python-web-wasm`, showing active use of Wasm in runtime and browser scenarios. | [wassette](https://github.com/microsoft/wassette)<br>[vscode-python-web-wasm](https://github.com/microsoft/vscode-python-web-wasm) |
| 5 | Docker / containerd | The container ecosystem uses Wasm through `runwasi`, the containerd project for running Wasm workloads alongside containers. | [runwasi](https://github.com/containerd/runwasi)<br>[Docker Wasm docs](https://github.com/docker/docs/blob/main/content/manuals/desktop/features/wasm.md) |
| 6 | Google Cloud | Google Cloud Service Extensions lets developers build inline networking extensions as Wasm modules using the Proxy-Wasm ABI. | [service-extensions-samples](https://github.com/GoogleCloudPlatform/service-extensions-samples) |
| 7 | Bytecode Alliance | Bytecode Alliance stewards major Wasm runtimes such as Wasmtime and WAMR that are used across cloud, server, and embedded environments. | [wasmtime](https://github.com/bytecodealliance/wasmtime)<br>[wasm-micro-runtime](https://github.com/bytecodealliance/wasm-micro-runtime) |
| 8 | wasmCloud | wasmCloud provides a cloud-native platform for running Wasm workloads across Kubernetes, clouds, datacenters, and edge environments. | [wasmCloud](https://github.com/wasmCloud/wasmCloud) |
| 9 | Fermyon / Spin | Fermyon created Spin, an open source framework for building and running cloud microservices with WebAssembly. | [spin](https://github.com/spinframework/spin) |
| 10 | WasmEdge / Second State | WasmEdge is a lightweight Wasm runtime used for cloud-native, edge, AI, and server-side workloads, with official runtime and examples published on GitHub. | [WasmEdge](https://github.com/WasmEdge/WasmEdge)<br>[wasmedge-containers-examples](https://github.com/second-state/wasmedge-containers-examples) |
| 11 | Kong | Kong uses WebAssembly in its Nginx-based WasmX module to extend proxy and API gateway behavior with Proxy-Wasm filters. | [ngx_wasm_module](https://github.com/Kong/ngx_wasm_module) |
| 12 | Solo.io | Solo.io publishes tooling, SDKs, and OCI packaging for Wasm modules used with Envoy-based gateways and service meshes. | [solo-io/wasm](https://github.com/solo-io/wasm) |
| 13 | SingleStore | SingleStore uses Wasm in its Code Engine so developers can run Wasm-based UDFs and TVFs inside the database engine. | [singlestore-wasm-toolkit](https://github.com/singlestore-labs/singlestore-wasm-toolkit) |
| 14 | SpinKube | SpinKube enables running Spin WebAssembly applications directly on Kubernetes through a dedicated containerd shim. | [containerd-shim-spin](https://github.com/spinkube/containerd-shim-spin) |
