# How is Wasm related to Docker


Traditionally, containers are built around operating system processes. This means that each container needs to have its own copy of the operating system, which can take up a lot of space and resources. Wasm containers, on the other hand, are much smaller and more lightweight. This is because Wasm code is compiled to a binary format that can be executed by any Wasm-compatible runtime.

As you mentioned, this makes Wasm containers ideal for running on shared environments. For example, Cloudflare can use Wasm containers to run dozens of different applications on a single machine. This is because each Wasm container only needs to take up the space of its own code and data, rather than the entire operating system.

In addition to being smaller and more lightweight, Wasm containers also start up much faster than traditional containers. This is because Wasm code does not need to be interpreted by the operating system. Instead, it is executed directly by the Wasm runtime.

The combination of smaller size, faster startup times, and the ability to run on shared environments makes Wasm a promising technology for containerization. As Wasm matures, it is likely to become more widely adopted for this purpose.

Here are some additional benefits of using Wasm for containerization:

- Security: Wasm code is sandboxed, which means that it cannot access the host operating system or other containers. This makes Wasm containers more secure than traditional containers.
- Performance: Wasm code is compiled to native code, which makes it very fast. This is especially important for applications that require high performance, such as games and real-time applications.
- Portability: Wasm code can be run on any platform that has a Wasm runtime. This makes it easy to deploy Wasm applications to any environment.

Overall, Wasm is a promising technology that has the potential to revolutionize containerization. 
It is smaller, faster, and more secure than traditional containers, and it can be run on any platform. 
As Wasm matures, it is likely to become more widely adopted for this purpose.
