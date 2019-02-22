<p align="center">
<img src="https://img.alicdn.com/tfs/TB1Tw1_ImzqK1RjSZFLXXcn2XXa-1400-797.png">
<a href="https://www.npmjs.com/package/@uform/react"><img src="https://img.shields.io/npm/v/@uform/react.svg"></a>
<a href="https://www.npmjs.com/package/@uform/antd"><img src="https://img.shields.io/npm/v/@uform/antd.svg"></a>
<a href="https://www.npmjs.com/package/@uform/next"><img src="https://img.shields.io/npm/v/@uform/next.svg"></a>
<a href="https://travis-ci.com/alibaba/uform"><img src="https://travis-ci.com/alibaba/uform.svg?branch=master"></a>
<a href="https://standardjs.com"><img src="https://img.shields.io/badge/code_style-standard-brightgreen.svg"></a>
</p>

***

> 面向复杂场景的中后台表单解决方案
>
> UForm 谐音 Your Form , 代表，这才是你想要的Form解决方案

## 背景

表单问题，不管是在jquery时代，还是angular/react时代，都永远是前端工程师们的痛，但是这又是没办法的事情，业务需求多种多样，对于中后台业务而言，表单页面和报表页面基本上是中后台业务的核心展现形式，但是，如何帮助开发者更高效的开发表单，目前传统的表单开发方式：

- 手动管理表单状态
- 手动收集表单数据
- 手动管理表单校验状态

带来的问题

- 表单状态管理变得越来越难以维护，不得已需要引入其他大而全的状态管理库，其实这仅仅只是一个领域性问题
- 当表单数量巨大的时候，如果每个表单都需要手动传入value/onChange，那是不能容忍的，同时传统表单开发的数据结构都是扁平结构，没法很好的处理嵌套复杂数据的情况，如果硬是要处理，工作量会变得越来越大
- 当表单校验规则存在联动校验的时候，要处理表单校验简直是噩梦，很容易产生大量的面条代码
- 当服务端有动态输出表单的需求的时候，你将不得不自己开发一个基于某个json协议动态输出表单的组件
- 当业务有对表单操作效率等指标的监控需求的时候，你将不得不自己开发一个基于某个json协议动态输出表单的组件来全局管理表单
- 当你希望在可视化搭建界面中快速配置产出表单的时候，你将不得不自己开发一个基于某个json协议动态输出表单的组件

## 方案

基于以上问题，也经历了漫长的表单领域的各种探索，最终我们沉淀出来 **UForm解决方案**

UForm是中后台领域的表单解决方案，覆盖了表单领域的各种布局，联动，校验场景，它集成了阿里内部fusion组件体系与antd组件，让您快速开发符合您业务体验需求的表单界面，您当然也可以通过UForm的扩展机制来快速接入自己团队的组件库。

UForm和核心特性：

- 基于标准JSON Schema协议，数据化构建表单
- 基于rxjs对表单内部的副作用做统一管理，轻松解决各种复杂联动校验场景
- 支持各种表单布局方案
- 支持可视化构建表单
- 支持自定义组件扩展
- 分布式状态管理，表单性能更高

## JSON Schema规范

想要快速了解JSON Schema，可以移步 [JSON-SCHEMA规范地址](http://gitlab.alibaba-inc.com/river/spec/blob/master/JSON-Schema.md)

## 为什么选用JSON Schema

选用JSON Schema，我们主要从以下几点来考虑：

- 我们的理念是希望用数据的思路来描述表单，而非前端组件树的思路来描述表单
- 标准化，因为它是目前业界最流行的数据结构描述语言，表单是Web系统的数据输入核心，所以采用JSON Schema也是一种最自然的选择

## 业界对比

目前来说业界比较流行的JSON schema驱动的React表单解决方案也就是mozilla家的 <https://github.com/mozilla-services/react-jsonschema-form>，但是，该方案存在几个问题：

- 强耦合bootstrap，不方便扩展
- json描述不能很好的在jsx中描述
- 没能很好的解决表单布局，表单联动的各种复杂问题
- 性能不行，内部数据管理走的React的全量rerender机制来做数据同步

当然，还有集团内部的[noform解决方案](https://alibaba.github.io/noform)，该方案同样也存在几个问题

- 单纯基于jsx描述表单，没办法数据驱动表单构建
- 性能不行，基于React的全量rerender机制做数据同步与表单联动
- 核心思路不够完备，从文档上来看，很难找到一个理念主线来串联整体设计

最后，再对比一下redux-form作者最近一直在持续更新的[final-form解决方案](https://github.com/final-form/final-form) ，UForm的核心设计思路其实也是参考的 final-form，可见它是非常优秀的一个表单解决方案，但是，因为它是属于jsx的表单解决方案，所以也不能支持数据化驱动，同时，在表单副作用管理上它也并没有一个完备的解决方案来管理，更多的是借助React自身的特性来解决副作用管理上的问题，而且，目前final-form也没有集成ant design或者fusion next这类强大的中后台组件体系，所以，如果您想从性能好，扩展性强，功能完备性，生态完备性这几个角度来选择表单解决方案的话，请选择 UForm吧！

## 谁在使用？

- 阿里供应链平台事业部
- 天猫
- 阿里云
- 阿里妈妈
- 盒马
- CBU
- 业务平台事业部
- ...

