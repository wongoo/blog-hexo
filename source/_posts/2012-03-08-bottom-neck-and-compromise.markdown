---
author: admin
comments: true
date: 2012-03-08 18:00:45+00:00
layout: post
slug: bottom-neck-and-compromise
title: 高性能系统思考－－系统瓶颈和资源认可性
wordpress_id: 230
categories:
- Inspiration
tags:
- high-performance
- 瓶颈
- 高性能
---


一个系统一般包含多个部分，各部分的性能和速度是差异的，整个系统的性能由性能最差的部分(瓶颈)决定。高性能的目的是让瓶颈的地方‘认可性’的扩大。

增加资源是可认可的。
实际很多系统情况是增加资源成本太高，客户更愿意扩大资源的认可性范围。

举个例子，本来需要从DB抓取更新实时数据，但对DB性能要求太高，无法实现。客户同意1分钟内有更新即可，即可增加缓存将数据缓存一分钟，同一个客户端一分钟只会请求一次db，其他都抓取缓存。但还是会出行大量同时请求的情况，db还不能承受此压力，已超出连接数。再次和客户讨论后客户同意10秒未获取db连接资源的情况可以直接返回缓存数据。 

通过两次扩大‘认可性’范围(也就扩大瓶颈)，系统每次请求可在10秒内返回，db的压力也不会变大，性能大大提高。

