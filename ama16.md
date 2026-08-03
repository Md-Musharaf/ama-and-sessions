# AMA Questions and Answers

## Boorle Sowmya Sri Lakshmi

### Question:
**What is a component in ReactJS?**

### Answer:
A **component** in ReactJS is a reusable, independent piece of the user interface (UI). Components allow developers to split the UI into smaller, manageable parts that can be reused throughout an application.

There are two main types of components:
- **Functional Components** – JavaScript functions that return JSX. They are the most commonly used components in modern React.
- **Class Components** – ES6 classes that extend `React.Component`. They were commonly used before React Hooks.

**Example:**
```jsx
function Welcome() {
  return <h1>Hello, World!</h1>;
}
```

---

## Nayunipatruni Harsha Vardhan

### Question:
**What is the difference between Docker and Kubernetes?**

### Answer:

| Docker | Kubernetes |
|--------|------------|
| Docker is a containerization platform used to create and run containers. | Kubernetes is a container orchestration platform used to manage containers at scale. |
| Runs individual containers. | Manages multiple containers across multiple servers. |
| Focuses on packaging applications. | Focuses on deployment, scaling, networking, and monitoring. |
| Suitable for small applications or development. | Suitable for large-scale, production-grade applications. |
| Does not automatically scale containers. | Supports automatic scaling and self-healing. |

**In short:** Docker creates containers, while Kubernetes manages and orchestrates them.

---

## Rongala Vasu

### Question:
**What are the advantages of using Docker over Virtual Machines?**

### Answer:

Docker has several advantages over Virtual Machines (VMs):

- **Lightweight:** Containers share the host operating system kernel, so they use fewer resources.
- **Fast Startup:** Containers start within seconds, whereas VMs take longer to boot.
- **Lower Resource Usage:** Multiple containers can run on a single machine with less CPU and memory usage.
- **Portability:** Docker containers run consistently across development, testing, and production environments.
- **Easy Deployment:** Applications and their dependencies are packaged together, reducing environment-related issues.
- **Efficient Scaling:** Containers can be started or stopped quickly based on demand.

**Summary:** Docker provides better performance, faster deployment, and more efficient resource utilization compared to Virtual Machines.

---

## Vikas Mehta

### Question:
**What is the main advantage of using Kubernetes over Docker?**

### Answer:

The main advantage of Kubernetes over Docker is **container orchestration**.

Kubernetes provides features such as:
- **Automatic scaling** of applications based on traffic.
- **Self-healing**, where failed containers are automatically restarted or replaced.
- **Load balancing** to distribute traffic across multiple containers.
- **Rolling updates and rollbacks** without downtime.
- **Service discovery and networking** between containers.
- **High availability** by running applications across multiple nodes.

**Summary:** Docker helps create and run containers, while Kubernetes automates the deployment, scaling, and management of those containers in production environments.
