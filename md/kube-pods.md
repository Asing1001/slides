# Kubernetes - pods

Note:
Hi i'm note, please press `s` to see note

---

## Pod

- A group of an application’s container, storage resources, a unique network IP, and spec that govern how the container(s) should run.

Note:
- The basic execution unit of a Kubernetes
- An environment the containers run in and persists until it is deleted. 
- Could use different container runtime other than Docker(default)

---

## Network

- Each Pod is assigned a unique IP address.
- Containers inside a Pod can communicate with one another using localhost
- Containers in a Pod can not use same ports

---

## Storage

- A Pod can specify a set of shared storage Volumes, container inside pod can access shared volume

---

## Lifecycle

- Does not reschedule, self-heal
- Has a Unique ID

Note:
containersReady vs ready?

---

## Benefits

- Management
- Resource sharing and communication


---

## Controller

---

## Example

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.7.9
        ports:
        - containerPort: 80
```

---

## More

- Pods does not self heal

---

## Thank you