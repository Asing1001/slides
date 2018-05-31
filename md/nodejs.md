# Nodejs guide

prepare by Andy Chen

Note:
Hi i'm note, please press `s` to see note

---

## Agenda

* Overview
* NodeJS Module
* Cluster
* NPM
* ExpressJS

---

## Feature

* JavaScript runtime
* Built on top of Chrome's V8 JS engine
* Single thread, event-driven, non-blocking I/O
* Node.js package ecosystem, NPM

---

## NodeJS Module

CommonJS - Require

1. Cache
2. Core module
3. Relative path (. or ..)
4. Absolute path (/)
5. node_modules

---

## Cluster

* Use multi-cpu to optimize performance
* Multi-process
* Master-child communication by [IPC](https://en.wikipedia.org/wiki/Inter-process_communication)
* [cluster.js demo](https://github.com/Asing1001/hello-node/blob/master/cluster.js)

---

## Event loop

* [Event loop](http://latentflip.com/loupe/)

---

## ExpressJS

* Middleware
* [firstExpress.js demo](https://github.com/Asing1001/hello-node/blob/master/firstExpress.js)
* http://expressjs.com/zh-tw/

---

## Reference

* [Cluster](https://nodejs.org/api/cluster.html)
* [深入淺出Nodejs](http://www.books.com.tw/products/0010644512)
* [Event loop](http://latentflip.com/loupe/)

---

## Q & A

---

## Thank you