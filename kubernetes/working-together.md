# Wasm and Kubernetes - Working Together


WebAssembly is a binary format that allows running code written in multiple languages (C/C++, Rust, Go, etc.) on the web. This format offers a fast, efficient, and safe way to execute code in the browser, and it is becoming increasingly popular for web development.

Kubernetes, on the other hand, is a popular open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications. Kubernetes is widely used for deploying and managing web applications in production environments.

## How Wasm workload runs on Kubernetes?

To run WebAssembly workloads on Kubernetes, we need two key components: 

- Worker nodes bootstrapped with a WebAssembly runtime and 
- RuntimeClass objects mapping to nodes with a WebAssembly runtime. 


![Image3](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/o5dpxd1mmpao4ftum0lc.png)



In this tutorial, we will explore how to use WebAssembly and Kubernetes together to build and deploy a sample app. We will walk you through the steps needed to set up a local environment, build a sample app using WebAssembly, and deploy it on a Kubernetes cluster.

## Step 1: Set up a Local Environment

Before we can start building our sample app, we need to set up a local environment for development. Here are the prerequisites:

- Docker
- Kubernetes CLI (kubectl)
- Rust programming language
- wasm-pack

You can install Docker and kubectl by following the official documentation. For Rust and wasm-pack, you can use Rustup, which is a toolchain manager for Rust. Once you have installed Rustup, run the following commands to install Rust and wasm-pack:

```
rustup default nightly
rustup target add wasm32-unknown-unknown
cargo install wasm-pack
```

## Step 2: Build a Sample App using WebAssembly

In this step, we will build a simple app using Rust and WebAssembly. This app will take two numbers as input and return their sum. Create a new Rust project using the following command:

```
cargo new wasm-app --lib
```

This will create a new Rust project called wasm-app with a library crate. Open the lib.rs file and add the following code:

```
use wasm_bindgen::prelude::*;

#[wasm_bindgen]
pub fn add(a: i32, b: i32) -> i32 {
    a + b
}
```

This code defines a function called add that takes two integers as input and returns their sum. The #[wasm_bindgen] attribute allows the function to be called from JavaScript.

Next, we need to compile the Rust code to WebAssembly. Run the following command to build the app:

```
wasm-pack build --target web --out-dir public
```

This will compile the Rust code to WebAssembly and place the output files in the public directory. The --target web option tells wasm-pack to build the app for the web, and the --out-dir public option specifies the output directory.

## Step 3: Create a Kubernetes Deployment

Now that we have built our sample app, it's time to deploy it on a Kubernetes cluster. For this, we need to create a Kubernetes deployment that runs the app inside a container.

Create a new file called deployment.yaml and add the following code:

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: wasm-app
spec:
  replicas: 1
  selector:
    matchLabels:
      app: wasm-app
  template:
    metadata:
      labels:
        app: wasm-app
    spec:
      containers:
      - name: wasm-app
        image: <DOCKER_USERNAME>/wasm-app:latest
        ports:
        - containerPort: 80
```

This code defines a Kubernetes deployment called wasm-app that runs one replica of the container image. The image field specifies the name of the Docker image that will be used to run the app, and the ports field specifies the port that the container will listen on (in this case, port 80).

Replace <DOCKER_USERNAME> with your Docker Hub username. If you don't have a Docker Hub account, you can sign up for free at https://hub.docker.com/.

Next, we need to build a Docker image for the app. Run the following command to build the image:

```
docker build -t <DOCKER_USERNAME>/wasm-app:latest .
```

This will build a Docker image for the app and tag it with your Docker Hub username and the latest tag.

## Step 4: Deploy the App on Kubernetes

Now that we have a Kubernetes deployment and a Docker image for the app, we can deploy the app on a Kubernetes cluster.

First, make sure that you have a Kubernetes cluster up and running. If you don't have one, you can create a local cluster using Minikube by following the official documentation.

Next, run the following command to apply the Kubernetes deployment:

```
kubectl apply -f deployment.yaml
```

This will create a new Kubernetes deployment called wasm-app and start one replica of the container image.

Finally, expose the app to the outside world by creating a Kubernetes service. Create a new file called service.yaml and add the following code:

```
apiVersion: v1
kind: Service
metadata:
  name: wasm-app
spec:
  selector:
    app: wasm-app
  ports:
    - name: http
      port: 80
      targetPort: 80
  type: LoadBalancer
```

This code defines a Kubernetes service called wasm-app that exposes the app on port 80. The type: LoadBalancer field tells Kubernetes to create a load balancer for the service so that it can be accessed from the internet.

Run the following command to apply the Kubernetes service:

```
kubectl apply -f service.yaml
```

This will create a new Kubernetes service called wasm-app and expose it on port 80.

## Step 5: Test the App

Now that we have deployed the app on a Kubernetes cluster, we can test it by sending HTTP requests to the Kubernetes service.

Run the following command to get the external IP address of the Kubernetes service:

```
kubectl get service wasm-app
```
This will display the external IP address of the Kubernetes service. Copy the IP address and open it in a web browser.

You should see a simple web page that allows you to enter two numbers and get their sum. This page is served by the app running inside the Kubernetes cluster.

## Conclusion

In this tutorial, we have explored how to use WebAssembly and Kubernetes together to build and deploy a sample app. We have walked you through the steps needed to set up a local environment, build a sample app using Rust and WebAssembly, and deploy it on a Kubernetes cluster.

WebAssembly offers a fast and efficient way to run code on the web, and Kubernetes provides a powerful platform for deploying and managing containerized applications. By combining these technologies, we can build and deploy web apps that are fast, scalable, and easy to manage.
