---
title: "0 days since YAML indentation error"
date: 2022-06-04T19:32:20+02:00
draft: false
---

![0 days](/images/0-days-since-yaml-indentation-error/cover.jpg)


Recently, I've started an online course about kubernetes. In one of the lessons we covered a topic of [initContainers](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/) and how we can use them to setup some stuff in our pod. The task was to start nginx with some index.html page downloaded from internet, and to use initContainers to download this page and put it as /usr/share/nging/html/index.html to be our starting page. Manifest of such pod is rather simple if you know where to put a tab :smile: I spent almost half an hour figuring it out why it didn't work, but finally I found this incorrect spacing, which I don't even remeber now where it was. Anyway here you have working example of pod with nginx with some content downloaded in init container

```
apiVersion: v1
kind: Pod
metadata:
  name: web
  labels:
    name: web
spec:
  containers:
  - name: web
    image: nginx
    ports:
      - containerPort: 80
    volumeMounts:
    - name: workdir
      mountPath: /usr/share/nginx/html
  initContainers:
  - name: install
    image: busybox
    command:
    - wget
    - "-O"
    - "/work-dir/index.html"
    - https://szymonprz.github.io/index.html
    volumeMounts:
    - name: workdir
      mountPath: "/work-dir"
  volumes:
  - name: workdir
    emptyDir: {}
```