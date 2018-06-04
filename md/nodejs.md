# Nodejs guide

prepare by Andy Chen

Note:
Hi i'm note, please press `s` to see note

---

## Agenda

* NodeJS feature
* NodeJS Module
* Cluster
* NPM
* ExpressJS

---

## Nodejs Feature

* A JavaScript runtime
* Built on Chrome's V8 JS engine
* Single thread, event-driven, non-blocking I/O
* Biggest package ecosystem, NPM

---

## NodeJS Module

Base on CommonJS module system

===

### Require type

* Directly module require e.g. `require('express')` 
    Will first check `built-in module`, then `node_modules` and `../node_modules` and `../../node_modules` until root folder.
* Path specific require `require('./my-module')` 
    Using when not `npm nodule` or `built-in module`
    
===

### Require order

1. Cache (Module will be stored in cache when first time require)
2. Built-in module
3. Current folder
4. Parent folder until root

===

### Require suffix

`require()` will automatically add `.js` `.json` `.node` suffix, it is suggested to add `.json` `.node` suffix so it would be found faster.

---

## Cluster

* Multi-CPU => Multi-process to optimize performance
* Will not crash when one process crashed
* Master-child process communicate by [IPC](https://en.wikipedia.org/wiki/Inter-process_communication)
* [cluster.js demo](https://github.com/Asing1001/hello-node/blob/master/cluster.js)

---

## Event loop

* [The concept of Javascript excution order - Event loop](http://latentflip.com/loupe/)

---

## ExpressJS

* Flow control by Middleware
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
