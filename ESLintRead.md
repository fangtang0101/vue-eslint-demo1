---
title: ESLint使用
author: 作者
top: false
toc: false
date: 2019-12-26 11:10:21
tags:
---

本文主要介绍 ESLint 的 基本概念，基本使用 demo的展示 以及在vue 中的使用，在Vscode 中的使用

<!--more-->

### ESLint 是什么

​	是一款针对javascript的**代码检查工具**

### ESLint 的一些基础知识

#### 规则 rule

> Eslint根据这个 rule 判断 目标 代码 是否 符合规范

- 官方提供的规则

  ```
  比如：no-console  等
  官方制定的规则 http://eslint.cn/docs/rules/
  ```

  请注意 绿色打钩  有修理符号的，都是有特殊意义的

  - 绿色打钩：当使用官方制定的规则去检查代码时，那么 会检查 绿色打钩的那些 规则
  - 修理符号：当检查出有问题的代码时，--fix 可自动修复 因该项 规则导致的 报警

  

- 也可以自定义

### ESLint 的基本使用（demo）

```
mkdir eslint_demo
cd eslint_demo
npm init
cnpm install --save-dev eslint
./node_modules/.bin/eslint --init
// init 的过程 会有很多选择选择项目 ，此选择的项目 就是 配置文件里面的参数的设置（设置如下）

// 出现一个 .eslintrc.js 的文件

```



- eslintrc.js 配置项目解读

  ```
  env: 环境变量的配置
  extends：规则的来源 （有点像 css 的引入的原则）
  	""  没有规则来源
  	eslint:all   官方所有
  	eslint:recommended 官方推荐
  	"./rule-free.js" 规则来源的 文件名称
  	"plugin:vue/essential"  插件，使用远程的 规则，一般都是 npm 里面，需要 install
  	
  globals：全局变量 ？？？
  plugin:['vue'] : 插件相关 ？？
  rules：{}   相当于内联css，权限比较高
  
  
  //http://eslint.cn/docs/user-guide/configuring
  parserOptions： 解析配置（主要是设置大的语言环境）
  	ecmaVersion：ECMAScript 版本，5 为默认，可设置 6，7，8，9 ... 或则 2018，1029
  	sourceType："script"(默认) 和 "module"
  	ecmaFeatures： 额外的特性配置
  		jsx
  		globalReturn
  		impliedStrict
  		experimentalObjectRestSpread
  		
  parser：// 选择解析器
  
  ```

  

- rules 中错误等级

  ```
  "quotes": ["error", "double"],
  
  具体规则（注意这个优先级更高，会更其他的文件中 rule合并）
  "no-console": "error" -> ”具体检查规则项目“：”错误等级“
          
  错误等级:
  - ”offer“ 或则 0  规则关闭，不生效
  - "warn" 或则 1   规则开启，警告而已
  - ”error“ 或则 2  规则开启，错误处理，退出程序（注意是退出程序，比方说Vue 压根就启动不了）
  
  double  ，双引号，具体的值
  ```

  

- 基本命令使用

  ```
  eslint xxx.js // 检查某个文件
  eslint --fix xxx.js //自动修复某个文件 错误
  eslint --ext .js, .vue src/     src 下面所有 .vue  与 .js 文件语法检查
  
  ```

  

- yyy

### ESLint 在Vue 中的使用

- eslint-plugin-vue

  此插件定义  vue 的 检验规则 rules，除非你自己写一套 vue的检验规则

  文档地址 https://github.com/vuejs/eslint-plugin-vue

  rules https://eslint.vuejs.org/rules/

  ```
  
  
  ```

- 如何使用

  ```
  npm i eslint --save-dev
  eslint -- init 
  (生成配置文件，选项中选择Vue和与该项目一直的环境即可，或则直接直接复制一份也行)
  npm i --save-dev eslint-plugin-vue
  eslint:[
  "eslint:recommended",
  "plugin:vue/essential"
  ]
  相当于引用了 rules 中的 essential的 规则
  越往下，越严格
   - base
   - essential
   - strongly-recommended
   - recommended
   - Uncategorized（为归纳的，需要自己定义）
   
   // lint 检查命令
   ./node_modules/.bin/eslint --ext .vue,.js src/
   
   
   
  ```

  

- vue   内部使用

  ```
  https://github.com/vuejs/eslint-plugin-vue-libs
  ```

  



### ESlint 在Vscode 的使用

