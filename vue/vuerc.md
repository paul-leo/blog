# Vue 3 预览版发布啦！

我们非常激动的宣布 Vue3.0进入预览版了！

进入预览版意味着核心的API和实现已经稳定了，原则上我们不期望在最终正式版发布之前介绍新的特性或者重大更新，大部分官方的框架已经支持V3，你可以在这里查看它们的最新状态[https://github.com/vuejs/vue-next\#status-of-the-rest-of-the-framework](https://github.com/vuejs/vue-next#status-of-the-rest-of-the-framework)  


## 新文档

Vue 的文档团队一直在更新V3的文档，现在已经可以使用了[https://v3.vuejs.org/](https://v3.vuejs.org/)，这是一个庞大的工作，非常感谢文档团队 [@NataliaTepluhina](https://github.com/NataliaTepluhina), [@bencodezen](https://github.com/bencodezen), [@phanan](https://github.com/phanan) and [@sdras](https://github.com/sdras). 努力的工作，新的文档已经精心的迁移了覆盖2和3的不同，在VuePress上运行，可在线编辑代码案例。

想快速浏览新版本相对于旧版本的改变，可查看  [Migration Guide](https://v3.vuejs.org/guide/migration/introduction.html).

需要注意的是新文档 对于迁移的知道仍然在工作中，我们会继续完善直到预览版发布





## 调试工具

我们发布了一个 全新的Vue 开发者调试工具用于初始化V3项目[https://github.com/vuejs/vue-devtools/releases/tag/v6.0.0-beta.1](https://github.com/vuejs/vue-devtools/releases/tag/v6.0.0-beta.1)  **感谢** [@Akryum](https://github.com/Akryum).

 开发者调试工具已经被重构成更好的解耦逻辑，接口也看起来是全新的，现在只有组件查阅功能，后续会有更多的功能

beta版本已经通过了Chrome 应用商店的审核 [https://chrome.google.com/webstore/detail/vuejs-devtools/ljjemllljcmogpfapbkkighbhhppjdbg](https://chrome.google.com/webstore/detail/vuejs-devtools/ljjemllljcmogpfapbkkighbhhppjdbg)  


##  快速试用

如果你现在就像使用Vue 3,你可以通过以下几个方案

* 在 [Codepen](https://codepen.io/team/Vue/pen/KKpRVpx) 上尝试
* 用 [Vite](https://github.com/vitejs/vite) 创建一个项目:

  ```text
  npm init vite-app hello-vue3
  ```

        Vite  在单文件组件中支持 [`<script setup>`](https://github.com/vuejs/rfcs/blob/sfc-improvements/active-rfcs/0000-sfc-script-setup.md) 和 [`<style vars>`](https://github.com/vuejs/rfcs/blob/sfc-improvements/active-rfcs/0000-sfc-style-variables.md)

* 我们已经提交了vue-cli支持V3 PR，很快就可以使用了

##  后续的工作

在预览版中我们还没有完全支持IE11，因此我们会继续这方面的工作

 同时我们主要的精力会转移到文档，迁移和兼容性上，我们现在的目标是提供一个简介的文档用于 创建一个全新的V3项目和类库作者升级他们的库，文档团队会基于社区的反馈继续完善迁移指引和V3的文档，

 迁移不重要的应用到V3 版本我们会在后续完成，我们会提供一些代码模块和工具帮助迁移，但是在大多数情况下这取决于应用的依赖有多快能够升级到支持V3，同样评估升级的风险和投入是否值得变得尤为重要，因为Vue 2仍然保持支持，我们计划在3.0发布后我们会把一些新的特性通过兼容性插件的形式“返工”到V2版本，我们已经有了一个成功的案例 [@vue/composition-api](https://github.com/vuejs/composition-api).

##  实验性的特性

 有一些特性在预览版和正式版已经包含了但是被标记成“实验性”的：

* `<Suspense>`
* [`<script setup>`](https://github.com/vuejs/rfcs/blob/sfc-improvements/active-rfcs/0000-sfc-script-setup.md)
* [`<style vars>`](https://github.com/vuejs/rfcs/blob/sfc-improvements/active-rfcs/0000-sfc-style-variables.md)

 这些特性以及在发布的版本中是为了收集在使用过程中的反馈,但是他们仍然有可能会有重大的修改和重大的评估，这些特性也有可能会保持“实验性”最终在3.1版本中正式采用

原文[https://github.com/vuejs/rfcs/issues/189](https://github.com/vuejs/rfcs/issues/189)

 

