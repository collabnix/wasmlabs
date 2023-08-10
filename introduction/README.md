## Overview of WebAssembly as a low-level, binary instruction format

![x866](https://github.com/collabnix/wasmlabs/assets/313480/b90943b2-3a6c-44b6-983c-25053843283d)




WebAssembly (often abbreviated as Wasm) is an open standard and low-level binary instruction format designed to execute code on the web. It serves as a portable compilation target for high-level languages like C, C++, Rust, and many others, enabling developers to run computationally intensive applications on the web platform with near-native performance.
Unlike traditional web technologies like JavaScript, WebAssembly is not a programming language but rather a binary format that represents code in a compact and efficient manner. It defines a stack-based virtual machine that executes the instructions directly, offering a fast and predictable runtime environment.
WebAssembly modules are typically compiled from higher-level languages into the binary format, making them more compact and efficient compared to equivalent JavaScript code. The binary format is designed to be fast to decode, optimizing load times and allowing for quick startup of applications.


## Which companies uses Wasm

Wasm is still considered to be a relatively new technology, but it is maturing rapidly. It is no longer considered to be experimental, and it is being used by a growing number of enterprises. As Wasm continues to mature, we can expect to see even more enterprises adopt it for a variety of use cases.

- Adobe: Adobe is using Wasm to power its new Edge Compute platform. This platform allows Adobe to deliver high-performance applications to users on the edge, without having to worry about the performance of the user's device.
- Microsoft: Microsoft is using Wasm in a number of its products, including Azure Functions, Visual Studio Code, and Edge. Azure Functions allows developers to run code on the edge without having to worry about the underlying infrastructure. Visual Studio Code is a popular IDE that supports Wasm development. And Edge is a web browser that supports Wasm, allowing developers to create high-performance web applications.
- Cosmonic: Cosmonic is a company that offers a Wasm-based cloud platform called wasmCloud. wasmCloud allows developers to deploy and run Wasm applications in the cloud.
- Fastly: Fastly is a CDN company that is using Wasm to improve the performance of its network. Wasm allows Fastly to cache and serve code more efficiently, which results in faster loading times for users.
- Cloudflare: Cloudflare is another CDN company that is using Wasm to improve the performance of its network. Cloudflare uses Wasm to accelerate the loading of images, videos, and other assets.

[Click Here to see the list of all companies](https://github.com/collabnix/wasmlabs/blob/main/whouseswasm/README.md)


## Is WebAssembly a VM?

WebAssembly (Wasm) is not a virtual machine (VM) itself, but it is often executed within a virtual machine environment.

WebAssembly is a binary instruction format designed to run efficiently in web browsers. It is designed as a low-level assembly-like language that allows code to be executed at near-native speed. WebAssembly code is typically generated from higher-level programming languages like C/C++, Rust, or TypeScript.

When executing WebAssembly code, it is typically run in a virtual machine called the WebAssembly runtime or engine. Examples of WebAssembly runtimes include V8 (used in Chrome and Node.js), SpiderMonkey (used in Firefox), and JavaScriptCore (used in Safari).

The WebAssembly runtime takes the WebAssembly bytecode as input and provides the necessary infrastructure to execute the code. It includes components like the bytecode interpreter, just-in-time (JIT) compiler, garbage collector, and other runtime features.

In summary, while WebAssembly itself is not a virtual machine, it is executed within a virtual machine environment provided by the WebAssembly runtime. This runtime enables efficient execution of WebAssembly code in web browsers and other environments that support WebAssembly.

## Comparison with other web technologies like JavaScript and asm.js

WebAssembly provides several advantages over other web technologies, including JavaScript and asm.js:

1. Performance: WebAssembly is designed for high performance, often surpassing the speed of equivalent JavaScript code. It achieves this by utilizing a compact binary format, efficient instruction set, and optimized execution engine.

2. Language Independence: Unlike JavaScript, which is the de facto language for web development, WebAssembly is language-agnostic. It can be generated from various programming languages, allowing developers to leverage their existing knowledge and choose the language that best fits their needs.

3. Compatibility: WebAssembly is designed to run alongside JavaScript, seamlessly integrating with existing web projects. It can be easily embedded into HTML documents and interact with JavaScript code, enabling incremental adoption and easy interoperability between the two.

4. Security: WebAssembly runs in a sandboxed environment, providing a layer of security by preventing direct access to the underlying system. It ensures that untrusted code from the web cannot perform malicious actions or compromise user data.

5. Size Efficiency: WebAssembly modules are highly compressed and smaller in size compared to equivalent JavaScript code. This results in faster downloads and reduced bandwidth consumption, especially for larger applications or games.

## Key features and advantages of WebAssembly

WebAssembly boasts several key features and advantages, including:

1. Efficiency: WebAssembly is designed for efficient execution, allowing complex computations and algorithms to run at near-native speeds. This performance improvement makes it suitable for computationally intensive tasks like gaming, simulations, multimedia processing, and cryptography.

2. Portability: WebAssembly is supported by multiple platforms, including web browsers, server-side environments like Node.js, and even embedded systems. This portability enables code reuse and deployment across various platforms without significant modifications.

3. Interoperability: WebAssembly seamlessly integrates with JavaScript and existing web technologies, providing a bridge between different programming languages and the web ecosystem. This interoperability allows developers to leverage existing libraries, frameworks, and APIs while gradually migrating code to WebAssembly.

4. Offline Execution: WebAssembly modules can be cached and executed offline, providing offline capabilities for web applications. This feature is particularly useful for web-based games, productivity tools, and applications that require consistent performance even in low-connectivity environments.

5. Ecosystem and Tooling: WebAssembly has a growing ecosystem with a wide range of tools and libraries available. Developers can find compilers, development frameworks, performance optimization tools, and debuggers specifically designed for WebAssembly, making development and deployment more convenient.

WebAssembly's combination of performance, language independence, compatibility, security, and size efficiency positions it as a powerful tool for modern web development, offering new possibilities and enhanced user experiences.

## How does Wasm work in browsers?


Browser engines, such as Google Chrome's V8 engine and Mozilla Firefox's SpiderMonkey, include a WebAssembly (Wasm) virtual machine or runtime. This runtime is responsible for executing the Wasm binary instructions within the browser environment.

To enable running existing applications or codebases in the browser, compiler toolchains like Emscripten come into play. Emscripten is a popular toolchain that can compile source code written in languages like C, C++, or Rust into the Wasm target. It translates the code into a format that can be understood and executed by the Wasm runtime in the browser.

By using Emscripten or similar tools, developers can port legacy applications, libraries, or game engines written in languages like C or C++ to run in the browser. This allows them to leverage the power of native languages and reuse existing codebases while seamlessly integrating with client-side JavaScript code in web applications.

The Wasm runtime provides an interface that enables communication between the Wasm module and the JavaScript code running in the browser. This allows bidirectional data exchange, function calls, and interactions between the Wasm module and the surrounding JavaScript environment.

Overall, WebAssembly provides a standardized and efficient format for running code in the browser, allowing developers to leverage existing codebases and bring powerful applications to the web platform.

![Untitled-2023-06-22-2312](https://github.com/collabnix/wasmlabs/assets/313480/e74d6bbc-fdbe-43d7-9626-102622a76bfe)




## How does Wasm work on servers?

In addition to running within the browser, WebAssembly (Wasm) can also be executed outside of the browser environment. This is made possible by Wasm runtimes that are designed to function on traditional operating systems like Linux, Windows, and macOS.

When running Wasm applications outside of the browser, the Wasm runtime needs to communicate with the host system using interfaces other than the JavaScript engine. One such interface is the WebAssembly System Interface (WASI). WASI provides a standardized way for Wasm modules to interact with the host system, similar to how applications interact with the operating system through POSIX interfaces.

WASI allows Wasm modules to perform various system-related operations, such as file I/O, network access, and interacting with system resources. By leveraging WASI, Wasm runtimes enable Wasm applications to communicate with the host system in a secure and controlled manner.

To facilitate the porting of existing POSIX-compliant applications to WebAssembly, projects like WASI SDK and wasi-libc have been developed. WASI SDK provides a toolchain and set of development tools for compiling POSIX applications to the Wasm target, while wasi-libc is a C library implementation that provides the necessary POSIX-compatible functions and system calls for Wasm modules.

By using WASI SDK and wasi-libc, developers can compile their existing applications, written in languages compatible with POSIX standards, to WebAssembly. This allows them to take advantage of the cross-platform nature of WebAssembly while reusing their existing codebases and benefiting from the performance and security advantages offered by WebAssembly.

In summary, Wasm runtimes that operate outside of the browser, coupled with the WASI interface and supporting tools like WASI SDK and wasi-libc, enable Wasm applications to interact with the host system and bring the power of WebAssembly to traditional operating systems in a portable and efficient manner.


![server](https://github.com/collabnix/wasmlabs/assets/313480/3f7dc5e1-9df2-4345-adc6-dc8faf2424f5)

## What about interpreted languages?

So far we have only mentioned compiled languages such as C and Rust can target WebAssembly. For interpreted languages such as Python, Ruby and PHP, the approach is different: their interpreters are written in C and can be compiled to WebAssembly. Then this interpreted compiled to Wasm can be used to execute the source code files, typically ending in .py, .rb, .php and so on. Once compiled to Wasm, any platform with a Wasm runtime will be able to run those interpreted languages even if the actual interpreter was never compiled for that platform natively.





