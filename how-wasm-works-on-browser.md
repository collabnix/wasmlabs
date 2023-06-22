## How does Wasm work in browsers?

Browser engines integrate a Wasm virtual machine, usually called a Wasm runtime, which can run the Wasm binary instructions. 
There are compiler toolchains (like Emscripten) that can compile source code to the Wasm target. This allows for legacy applications to be ported to a browser and directly communicate with the JS code that runs in client-side Web applications.

![image](https://github.com/collabnix/wasmlabs/assets/313480/1415a090-bf15-4999-b344-d8335fd19320)

Source ~ https://wasmlabs.dev/articles/docker-without-containers/
