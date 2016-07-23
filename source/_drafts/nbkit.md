---
title: 一个新的轮子——nbKit
tags:
---

	内部使用，这里只记录思路
# what
一个移动端前端组件集合及配套构建工具，基于react，redux，webpack。Short for New Business Kit。
# why
* 按页面打包，支持首屏后端渲染，其后对支持pushState的浏览器SPA。
* 业务组件与通用组件分离，并尽可能多的从业务组件中提取通用组件。少通用，多定制。
* 支持物理后退劫持以及业务后退逻辑分支。
* 定制hybrid（Qunar App）行为
# how
* 大小写敏感：
git config core.ignorecase
https://github.com/Urthen/case-sensitive-paths-webpack-plugin
* 编译好的node-sass：
https://github.com/sass/node-sass-binaries/




