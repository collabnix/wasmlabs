## Overview of WebAssembly as a low-level, binary instruction format

![x86](https://github.com/collabnix/wasmlabs/assets/313480/87b9799f-7e96-43a3-af1c-9e5e5227398e)




Companies like Vercel, Fastly, Shopify, and Cloudflare support using Wasm for running code at the edge, and Fermyon is building a platform to run Wasm microservices in the cloud. 


WebAssembly (often abbreviated as Wasm) is an open standard and low-level binary instruction format designed to execute code on the web. It serves as a portable compilation target for high-level languages like C, C++, Rust, and many others, enabling developers to run computationally intensive applications on the web platform with near-native performance.
Unlike traditional web technologies like JavaScript, WebAssembly is not a programming language but rather a binary format that represents code in a compact and efficient manner. It defines a stack-based virtual machine that executes the instructions directly, offering a fast and predictable runtime environment.
WebAssembly modules are typically compiled from higher-level languages into the binary format, making them more compact and efficient compared to equivalent JavaScript code. The binary format is designed to be fast to decode, optimizing load times and allowing for quick startup of applications.

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

Browser engines integrate a Wasm virtual machine, usually called a Wasm runtime, which can run the Wasm binary instructions. 
There are compiler toolchains (like Emscripten) that can compile source code to the Wasm target. This allows for legacy applications to be ported to a browser and directly communicate with the JS code that runs in client-side Web applications.

![Untitled-2023-06-22-2312](https://github.com/collabnix/wasmlabs/assets/313480/e74d6bbc-fdbe-43d7-9626-102622a76bfe)




## How does Wasm work on servers?


There are Wasm runtimes that can run outside of the browser, including traditional operating systems such as Linux, Windows and macOS. Because they cannot rely on a JavaScript engine being available they communicate with the outside world using different interfaces, such as WASI, the WebAssembly System Interface. These runtimes allow Wasm applications to interact with their host system in a similar (but not quite the same) way as POSIX. Projects like WASI SDK and wasi-libc help people compile existing POSIX-compliant applications to WebAssembly.


![image](https://github.com/collabnix/wasmlabs/assets/313480/b86e79c7-a8d7-43fe-b86c-18ef4554e3d2)

[Source](https://wasmlabs.dev/articles/docker-without-containers/)

## What about interpreted languages?

So far we have only mentioned compiled languages such as C and Rust can target WebAssembly. For interpreted languages such as Python, Ruby and PHP, the approach is different: their interpreters are written in C and can be compiled to WebAssembly. Then this interpreted compiled to Wasm can be used to execute the source code files, typically ending in .py, .rb, .php and so on. Once compiled to Wasm, any platform with a Wasm runtime will be able to run those interpreted languages even if the actual interpreter was never compiled for that platform natively.

![image](https://github.com/collabnix/wasmlabs/assets/313480/2033c361-b12e-45ee-870c-0599cf0f949d)

[Source](https://wasmlabs.dev/articles/docker-without-containers/)


