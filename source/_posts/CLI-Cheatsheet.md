---
title: CLI操作技巧
date: 2016-07-31 20:07:41
tags:
---

# 给使用Mac同学的建议
1. 使用 iTerm2
2. 给iTerm2修改`option`键为`escape` https://www.iterm2.com/faq.html

# 导航快捷键
兼容键布局下`escape`指代`alt`。
大多数文本编辑器都使用了类似的键绑定，比如印象笔记，sublime。
_**Mac下，以下快捷键在所有没有修改键绑定的文本输入框都可能适用（按单词跳动一般为`option` + `←`/`→`），比如Chrome的地址栏、输入框、开发者工具的控制台；Finder的goto；……**_
## 移动
|按键|含义|
|---|---|
|`ctrl` + `E` | 移动光标到行末 |
|`ctrl` + `A` | 移动光标到行首 |
|`ctrl` + `←` | 向前跳一个单词（按空格分词）|
|`escape` + `B` | 同上（`ctrl` + `←`/`→`在Mac下，默认是系统级快捷键，用于切换工作区） |
|`ctrl` + `→` | 向后跳一个单词（按空格分词）|
|`escape` + `F` | 同上 |

## 剪切粘贴与删除
|按键|含义|
|---|---|
|`ctrl` + `U` | 剪切光标前至行首的内容 |
|`ctrl` + `K` | 剪切光标至行末的内容 |
|`ctrl` + `W` | 剪切光标前一个单词 |
|`ctrl` + `Y` | 粘贴 |
|`escape` + `backspace`| 删除前一个单词 |

# 继续使用上一个命令

	!!

最常见的应用场景是提示你没权限，下面这个命令代表 "sudo "+ lastCommand
	sudo !!

_**所有叹号标记（exclamation point）都和上面的例子一样，可以做字符串拼接**_

# 最近一次使用的以`[string]`开头的命令

	![string]

相当于只能查以`[string]`开头的 `ctrl` + `R`，但没有办法用`↑`和`↓`进行选择了。
如果不执行只是先看看：

	![string]:p

例如我在跳板机上想执行最近一次的ssh命令，但需要先确认一下

	!ssh:p

如果输出没问题，直接可以用 `!!`执行

# 从历史中选择执行的命令

	![number]
	
先 ``history | grep xxx`` 拿到命令事件序号后再使用

# 继续使用上一个命令的入参
| 叹号标记 | 含义 |
|---|---|
| !^ | 第一个参数 |
| !$ | 最后一个参数 |
| !* | 所有的参数 |
| !:2 | 第二个参数 |
| !:2-3 | 第二至第三个参数 |
| !:2-$ | 第二至最后一个参数 |
| !:2* | 第二至最后一个参数 与上一个等价 |
| !:2- | 第二至最后一个之间的参数 与前两个的不同之处在于不包含最后一个参数 |
比如新建一个目录并cd进入

	sudo mkdir -p /etc/log/nginx/ 
	cd !$

# 继续使用上一个命令的出参
管道符`|`

## 管道符使用举例
假设有一个日志文件 test.log

> [2016-07-01 08:10:00] userA visit indexPage
> [2016-07-01 08:10:10] userB visit indexPage
> [2016-07-01 08:10:15] userA visit listPage
> [2016-07-01 08:10:20] userC visit indexPage
> [2016-07-01 08:10:25] userB visit listPage

现在想知道都有哪些用户访问了indexPage？

1. 首先以indexPage作为筛选

		grep indexPage test.log
	得到：
	> [2016-07-01 08:10:00] userA visit indexPage
	> [2016-07-01 08:10:10] userB visit indexPage
	> [2016-07-01 08:10:20] userC visit indexPage
	
2. 然后将上一步的结果按空格分列，将第三列输出

		grep indexPage test.log | awk '{print $3}'
	得到：
	> userA
	> userB
	> userC

# 用扩展填充当前命令

命令中经常可以提取公因式
比如新建存储3种像素密度图片的文件夹:

	mkdir image@1x image@2x image@3x

更好的方案是:

	mkdir image@{1,2,3}x
	
	
再比如在nginx的config目录下，使用nginx的默认配置文件:

	mv nginx.conf.default nginx.conf
	
更好的方案是：

	mv nginx.conf{.default,}
	
_*注意：如果用叹号标记取扩展命令的参数，取到的是扩展之前的*_

# 其他
|按键|含义|
|---|---|
|`ctrl` + `R`|按关键词搜索命令历史，关键词可以出现在命令的任何地方。可以用`↑`和`↓`进行选择|
|`tab`|自动完成|
|`↑`/`↓`|从命令历史中选择|

