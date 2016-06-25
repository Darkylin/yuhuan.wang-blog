---
title: 前端新人培训
date: 2016-06-09 16:50:26
---

# 前言
## 为什么选择前端
面试中一般听到的答案无外乎以下:
* 最贴近用户
* 所见即所得
* 上手容易
* 炫酷的动画很容易获得成就感

都没错，前端是用户和后端的桥梁，人机交互界面的实施者。我觉得前端的魅力在于尚没有范式垄断，更新快，没有普适标准，于是我们有机会去深入，去陪伴他的迭代。
所以作为前端，不能固步自封安于现状，只有不断学习，思考，创造。

## 作为前端，需要具备哪些基本素养
### 清楚自己知识的边界
与现实世界不同，软件的世界是人类创造的，这里的一切都遵循着已经文档化的或代码化的规范。
知识的边界指的是我知道哪些，熟悉哪些，掌握哪些，精通哪些，不知道哪些。千万别对我说`我不知道的东西怎么知道自己知不知道`。
当和别人探讨方案的时候，如果跟不上对方的步调，对某些名词存疑，一定要第一时间提出。
有效的沟通是对沟通双方的尊重，尽一切努力来避免在沟通后出现模棱两可的结论。
> 知道: 听闻，知道大概，不清楚的部分能通过搜索引擎解决。
> 了解/熟悉: 写过demo，部分使用细节不甚清楚。
> 掌握: 实际应用过或写过demo，使用不成问题。
> 精通: 读过源码，对所有使用case心中有数，对可能出现的bug如数家珍。
> 不知道: 没有概念，完全无从下手。

### 求知欲
曾经很多人对待编程的态度是复制粘贴，因为从商业角度来说，永远是结果优先，实现功能再说。但如果总是这种态度，势必会玩火自焚，因为你驾驭不了。这种问题在大型项目的维护过程中会更加突出。
我并不是否决这种能够快速进入前端的方式，只是想提醒善于copy改的你，尽快透过现象看本质。任何一门人造学科都是潜得越深，飞得越高。
*最可怕的事莫过于你不想一探究竟*。

### 时间管理
时间对于我们并不公平，因为年龄经验际遇不一样。但并不能因为这个就放弃。下班后，休息日，当时间属于自己的时候，你怎样支配时间将决定你的未来。除去陪家人朋友和伴侣的时间，我有个不成熟的小建议:如果你预感即将做的这件事，3个月后自己将会完全忘记，留不下任何涟漪，那就把这部分时间攒起来去学习吧。千万别拿五谷轮回等生理需求跟我抬杠。我只是试图怂恿你把更多的时间投入到学习和反思中去。

### 反思
一味的冲，后劲会不足。所以我们偶尔应该停下脚步，去整理下行囊:这段时间有了哪些收获，哪些体悟。知识是前人的经验与总结，对于人造学科，可能是一个世界观与绝对方法论。但我们在汲取养分的时候，一定要自己做判断，形成自己的体系。一个领域的专家不会是另一个领域的白痴。学习最重要的事是掌握事物内部的规律与联系，比如学习一个新框架，表面的学是学习API的用法，深入的学则是作者为什么设计了这些API，这些API解决了哪些问题，还有哪些问题。答案可以通过讨论或者查看change log来进行印证。

### 写demo
学会写demo，不是抄示例代码，是自己构想应用场景，并将刚刚所学应用于实践。在经验不足的时候，不动手是很难发现问题的。写demo可以帮我们构建一条知识与实际的链路，这将在工作中提供有力支撑。
> 纸上得来终觉浅，绝知此事要躬行。《冬夜读书示子聿》

# 对于新人，你需要掌握的知识
## [HTML](https://developer.mozilla.org/zh-CN/docs/Web/HTML)
作为标记语言，HTML部分我们最在意一件事就是标签语义化。因为源码的目标用户是浏览器和搜索引擎爬虫，语义化指的就是让他们理解html中各段代码的作用，内容的层级。
## [CSS](https://developer.mozilla.org/zh-CN/docs/Web/CSS)
## [Javascript](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)
## 如何去搜索
google关键字。提炼关键字是一个很需要经验的能力，所以建议你多阅读相关社区，博客，文档。

# 你需要了解的知识
## 应用层框架
### [react](http://reactjs.cn/react/docs/getting-started.html)
用状态机的思路来解决DOM变更，每次渲染都是一个`关键帧`。相较于jQuery时代，展示逻辑更易维护。
代码片段天然即是组件。
### [redux](http://cn.redux.js.org/)
数据集中管理，业务逻辑更加集中。与react配合默契，为react props变更提供另一个统一出口。

## 基础
### [ES6](http://es6.ruanyifeng.com/)
### 浏览器调试器
我习惯用[Chrome的DevTools](https://developer.chrome.com/devtools)。
### 手机远程调试
* 浏览器自带: [chrome]、[safari]
* 第三方: [browsersync(wenire)][browsersync]、[JSConsole]、[vorlonjs]
* 打桩: 主要用于确定是哪部分代码的原因导致结果不符预期，可以用二分法打桩alert，有弹窗代表代码执行到了这里，上面的代码没问题。
* 全局onerror:

``` javascript
    window.onerror = (...e) => alert(JSON.stringify(e, false, 2));
```

### [IDE]
组内使用[webstorm]， 所以学吧。
### [nodejs]
### 版本控制
[git]
### 翻墙
taobao很多，我用的是: http://vip.yingsuo.cc/

# 你需要知道的知识
## 规范
js包含三部分:BOM DOM ES， 在H5前，BOM无规范，主要靠浏览器自觉;DOM是w3c规范;ES如其名，是ECMA规范。WHATWG在HTML5中对DOM和BOM做了修订与补充，是现行规范。规范是给浏览器厂商准备的，但了解了这些可能会让我们能更好的解决问题。

* [HTML5](https://html.spec.whatwg.org/) [API速查](http://html5index.org/)
* [ECMAScript2015]
* 如果想看w3c规范，先学下: [怎么读w3c文档](http://alistapart.com/article/readspec)

## [bash常用命令](http://www.freeos.com/guides/lsst/)
## [nginx与反向代理](http://nginx.org/en/docs/beginners_guide.html)
## UI与UE
这需要一点美学，平时多看多想。*先会抄再去评最后创造。*

# 题外话
建议你使用macbook，osx相比windows对node社区支持更完善。


[safari]: https://developer.apple.com/library/safari/documentation/AppleApplications/Conceptual/Safari_Developer_Guide/GettingStarted/GettingStarted.html
[chrome]: https://developers.google.com/web/tools/chrome-devtools/debug/remote-debugging/remote-debugging
[ide]: http://www.slant.co/topics/1686/compare/~webstorm_vs_atom_vs_sublime-text
[git]: http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000
[jsconsole]: http://jsconsole.com/
[volonjs]: http://vorlonjs.com/
[browsersync]: https://www.browsersync.io/
[webstorm]: https://www.jetbrains.com/help/webstorm/11.0/quick-start-guide.html
[nodejs]: https://nodejs.org/docs/v4.2.4/api/
[ECMAScript2015]: http://www.ecma-international.org/publications/files/ECMA-ST/Ecma-262.pdf

