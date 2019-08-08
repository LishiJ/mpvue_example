# mpvue

> A Mpvue project

它的目标是：在未来最理想的状态下，可以一套代码可以直接跑在多端：WEB、微信小程序、支付宝小程序、Native（借助weex）。不过由于各个端之间都存在一些比较明显的差异性，从产品的层面上讲，不建议这么做，这个框架的官方他们对它的期望的也只是开发和调试体验的一致。

## What Can Do 

- 彻底的组件化开发能力：提高代码
- 完整的 Vue.js 开发体验
- 方便的 Vuex 数据管理方案：方便构建复杂应用
- 快捷的 webpack 构建机制：自定义构建策略、开发阶段 hotReload
- 支持使用 npm 外部依赖
- 使用 Vue.js 命令行工具 vue-cli 快速初始化项目
- H5 代码转换编译成小程序目标代码的能力


## Build Setup

``` bash
# 初始化项目
vue init mpvue/mpvue-quickstart myproject
cd myproject

# 安装依赖
yarn

# 开发时构建
npm dev

# 打包构建
npm build

# 指定平台的开发时构建(微信、百度、头条、支付宝)
npm dev:wx
npm dev:swan
npm dev:tt
npm dev:my

# 指定平台的打包构建
npm build:wx
npm build:swan
npm build:tt
npm build:my

# 生成 bundle 分析报告
npm run build --report
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
