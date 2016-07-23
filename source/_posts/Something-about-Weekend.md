---
title: Something about Weekend
date: 2016-07-23 19:42:08
---

# 2016年7月 第4周
## case： 
webpack配置项中有一个叫[entry]的，有一个叫[context]的，现在你要实现context对entry的影响。
## more： 
1. 执行环境：node4
2. context配置的是entry基于的目录，假设配置为'/project'。
3. entry配置的是入口文件，值可能为
	* 字符串如：`entry: './page1'` 经过处理应得出：`entry: '/project/page1'`
	* 数组如： `entry: ['./entry1', './entry2']` 经过处理应得出：`entry: ['/project/entry1', '/project/entry2']`
	* 对象如： 

		```js
			entry: {
			   page1: './page1',
			   page2: ['./entry1', './entry2']
			}
		```
		
		经过处理应得出： 
		
		```js
			entry: {
			   page1: '/project/page1',
			   page2: ['/project/entry1', '/project/entry2']
			}
		```
4. 工具类尽量使用lodash。

[entry]:https://webpack.github.io/docs/configuration.html#entry
[context]:https://webpack.github.io/docs/configuration.html#context

****



