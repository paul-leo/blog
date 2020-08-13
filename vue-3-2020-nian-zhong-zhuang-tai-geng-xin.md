# Vue 3: 2020年中状态更新

## Vue 3: 2020年中状态更新

很多用户问我们一个问题：Vue3什么时候会发布？我们尽量避免给出一个明确的答案，因为预测软件的截至日期通常是不准确的。作为一个非盈利的项目，我们一直想关注于写一个好的软件而不是赶截至日期。然而，这会是一个漫长的等待，我们也知道不确定因素会使指定Vue3的计划变得困难，因此这儿我们更想提供一些通用的指导意见和详细的状态更新帮助用户满足对Vue的期待和调整相应的计划。

我们的在设计和构建Vue3的稳定的核心上花费了很大一部分时间，在这个过程中会迸发出一些令人激动的灵感（如果你想了解更多可查看[https://increment.com/frontend/making-vue-3/](https://increment.com/frontend/making-vue-3/)），为了让整个框架变成“ready”的状态，我们要做的不仅仅是核心，我们还需要做出一个能够兼容现有生态的版本，比如类库（Vue Router,Vuex,test utils），开发工具（CLI,eslint plugin,浏览器调试扩展，IED扩展），还有文档（同时兼顾新手和旧版本迁移过来的用户），当我们一直在努力做这些工作的时候，给出一个包含这些所有的琐碎的事情的时间线变得非常困难，我们本来希望在2020年上半年的时候能够发布正式版，但是我们不得不根据当前的进度做出调整。我们现在的目标时间是在七月中旬的时候有一个预览版，在八月初的时候能有一个3.0的官方正式版

## 决策树

 这并意味着着现在不能开始使用Vue 3，因为框架的大部分功能已经是beta或者alpha阶段了，而且核心部分已经经过了早期的试用者实践的检验，现在唯一卡住我们没有发布预览版的是浏览器的调试工具（我们正在努力积极的做这件事）所有的重大更新已经得到落地并且在PFCs中有记录，我们的计划不会在有新的重大变动了，如果你想早点用上Vue3，这儿有一个决策树可以帮助你适配我们的计划



```javascript
IWantVue3()

async function IWantVue3() {
  await read(`https://github.com/vuejs/rfcs/pulls?q=is%3Apr+is%3Amerged+label%3Acore+-label%3Arevoked+-label%3A2.6+sort%3Acomments-desc`)

  if (isTrue("I just want to play with Vue 3"))) {
    // If you just want to try Vue 3 out - you can do it right now with Vite.
    // Vite (https://github.com/vitejs/vite) is a new dev/build tool that we
    // created that is lighter, faster and produces smaller bundles. It works
    // with Vue 3 out of the box.
    run(`npm init vite-app hello-vue3`)
    return
  }

  if (isTrue("I am planning to use Vue 3 for a new project")) {
    if (isTrue("I need IE11 support")) {
      await IE11CompatBuild() // July 2020
    }
    if (isTrue("RFCs are too dense, I need an easy-to-read guide")) {
      await migrationGuide() // July 2020
    }
    if (isTrue("I'd rather wait until it's really ready") {
      await finalRelease() // Targeting early August 2020
    })
    run(`npm init vite-app hello-vue3`)
    return
  }

  if (isTrue("I am planning to upgrade an existing Vue 2 project")) {
    await IE11CompatBuild()
    await migrationGuide()
    await ecosystem(
      // this is the tricky part: if you have an existing, non-trivial Vue 2
      // app, you likely are using some dependencies that are not yet
      // Vue-3-compatible, for example meta frameworks like Nuxt, or UI
      // component libraries like Vuetify. If that's the case, our suggestion
      // is don't be in a hurry to upgrade. It *will* take some time for the
      // ecosystem to catch up.
      // Also note that you can start using Vue Composition API in Vue 2 today
      // via https://github.com/vuejs/composition-api - we are also going to be
      // backporting compatible Vue 3 features to 2.x once 3.0 is out.
    )
    return
  }

  if (isTrue("I am the author of a Vue ecosystem library")) {
    // It's time to make your lib Vue 3 compatible!
    return
  }
}
```



##  框架主要部分的状态

###  Vue 3 Core

* [![beta](https://camo.githubusercontent.com/35043cce2a552b9c29e6e2267f4c9c9baec31090/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f762f7675652f6e6578742e737667)](https://www.npmjs.com/package/vue/v/next)
* [Github](https://github.com/vuejs/vue-next)
* [RFCs](https://github.com/vuejs/rfcs/pulls?q=is%3Apr+is%3Amerged+label%3Acore)

Vue 3 的内核已经进入beta版本两个月了，我们已经合并了所有计划的重大更新，而且在正式版发布之前不会有重大更新了

上千的早期试用者已经在新项目中使用，并且帮助我们修复了很多bug和一些与旧版本表现不一致的地方，现如今我们相信Vue3 的内核是相当稳定的并且已经做好了预发版的准备。

### 、

#### Vue Router

* [![alpha](https://camo.githubusercontent.com/8c14172146de976291c555b24839bd6e7f65a3a7/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f762f7675652d726f757465722f6e6578742e737667)](https://www.npmjs.com/package/vue-router/v/next)
* [Github](https://github.com/vuejs/vue-router-next)
* [RFCs](https://github.com/vuejs/rfcs/pulls?q=is%3Apr+is%3Amerged+label%3Arouter)

 我们任然有一个次要的路由钩子表现不一致的问题，但是这是唯一卡住我们发布测试版的原因，目前路由对于一个新的，非关键的项目是可用的。

 

#### Vuex

* [![beta](https://camo.githubusercontent.com/fbf0df4356b468846273e602cac7c43ef6fe7d5d/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f762f767565782f6e6578742e737667)](https://www.npmjs.com/package/vuex/v/next)
* [Github](https://github.com/vuejs/vuex/tree/4.0)

Vuex4.0和3.x唯一的区别在是Vue3的兼容性！已经准备好和Vue 3 Core一起发布预览版

#### Vue CLI

目前 [vue-cli-plugin-vue-next](https://github.com/vuejs/vue-cli-plugin-vue-next) 插件是支持Vue3 的，你可以构建一个新的项目通过运行 vue add vue-next 切换到Vue3项目，在创建项目的过程中会出现是否使用Vue3的选项；

#### JSX Support

为了适应Vue3中略微有一些不同的语法现在有两个JSX transform 选择，。我们用这个 [帖子](https://github.com/vuejs/jsx/issues/141) 来统一Vue3的设计并且落地到官方的规范，如果你使用JSX，欢迎你在这个贴子中反馈给我们



#### Other Projects

| Project | Status |
| :--- | :--- |
| vue-devtools | WIP \(beta channel with Vue 3 support in early July\) |
| eslint-plugin-vue | [![alpha](https://camo.githubusercontent.com/7dc2a967c0c73760ff7a9e82b369f398a4e68e49/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f762f65736c696e742d706c7567696e2d7675652f6e6578742e737667)](https://www.npmjs.com/package/eslint-plugin-vue/v/next) \[[Github](https://github.com/vuejs/eslint-plugin-vue)\] |
| @vue/test-utils | [![alpha](https://camo.githubusercontent.com/c34759c47bb03b0f8a6476e11a67c44263551169/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f762f407675652f746573742d7574696c732f6e6578742e737667)](https://www.npmjs.com/package/@vue/test-utils/v/next) \[[Github](https://github.com/vuejs/vue-test-utils-next)\] |
| vue-class-component | [![alpha](https://camo.githubusercontent.com/fc82739bb3325866c2a1d1f5cef0bd9716ad1a48/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f762f7675652d636c6173732d636f6d706f6e656e742f6e6578742e737667)](https://www.npmjs.com/package/vue-class-component/v/next) \[[Github](https://github.com/vuejs/vue-class-component/tree/next)\] |
| vue-loader | [![alpha](https://camo.githubusercontent.com/28112db8b90cc6b6690bf4c08cec9e996b2f7c18/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f762f7675652d6c6f616465722f6e6578742e737667)](https://www.npmjs.com/package/vue-loader/v/next) \[[Github](https://github.com/vuejs/vue-loader/tree/next)\] |
| rollup-plugin-vue | [![alpha](https://camo.githubusercontent.com/ae1916f09be64023634f22995210dd4115b12f22/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f762f726f6c6c75702d706c7567696e2d7675652f6e6578742e737667)](https://www.npmjs.com/package/rollup-plugin-vue/v/next) \[[Github](https://github.com/vueComponent/jsx)\] |









