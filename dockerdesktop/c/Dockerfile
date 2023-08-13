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
