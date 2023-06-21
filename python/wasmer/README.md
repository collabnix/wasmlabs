
# Getting Started with Wasmer - A WebAssembly Runtime for Python Developers

This tutorial will guide you through the process of getting started with Wasmer, a WebAssembly runtime for Python. Wasmer allows you to run WebAssembly modules securely and efficiently in your Python applications.

## Installation

To begin, you need to install the wasmer Python package and the wasmer_compiler_cranelift compiler. Open your terminal and run the following command:

```
pip install wasmer wasmer_compiler_cranelift
```

## Usage

Let's dive into a simple example that demonstrates how to use Wasmer to execute a WebAssembly module in Python:

```
from wasmer import engine, Store, Module, Instance

# Create a store to hold our WebAssembly module
store = Store()

# Compile the WebAssembly module
module = Module(store, """
(module
  (type (func (param i32 i32) (result i32)))
  (func (export "sum") (type 0) (param i32) (param i32) (result i32)
    local.get 0
    local.get 1
    i32.add))
""")

# Instantiate the compiled module
instance = Instance(module)

# Call the exported `sum` function with arguments
result = instance.exports.sum(5, 37)

# Print the result
print(result)  # Output: 42
```

Save the above code in a file (e.g., simple.py) and run it using the following command:

```
python simple.py
```

The example demonstrates how to compile a WebAssembly module and execute a function from it using Wasmer. The sum function takes two integers as parameters and returns their sum. In this case, it adds 5 and 37, resulting in 42.

## Additional Resources

To explore more examples and learn about advanced features, refer to the official documentation provided with the Wasmer package. The documentation is packed with detailed explanations and additional code samples to help you understand and utilize Wasmer effectively.

You can also join the Wasmer Slack community and participate in the #python channel to connect with other developers, ask questions, and get support.

Remember to check PyPI for the latest version of the Wasmer Python package and download statistics.

## Conclusion

Congratulations! You have completed the tutorial and learned how to use the Wasmer runtime to execute WebAssembly modules in Python. You can now start exploring more complex WebAssembly applications and use cases.

Happy coding with Wasmer and Python!
