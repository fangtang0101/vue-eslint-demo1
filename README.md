# vue-eslint-demo1

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).



### 安装
npm i --save-dev eslint
./node_modules/.bin/eslint --init (选择 vue 会安装 eslint-plugin-vue)
"eslint":"eslint --ext .js,.vue src/"

### 测试步骤
1. 在rules 中 创建  规则  "no-console":"error"
2. 随便在 某个 .vue 中增加 console.log
3. npm run eslint 
4. 将 rules 中 规则 去除，再次运行 npm run eslint 即可看到效果

### 测试 eslint-plugin-vue 的作用
https://eslint.vuejs.org/rules/
验证 no-dupe-keys
1. 在 methods 中 添加 foo(){}  方法，在 computed 中增加 foo(){}  计算属性
2. 运行 npm run eslint 发现报错


### VScode 根据 eslint的规则提示
1. 下载 eslint 插件
2. 在 code - 首选项 - 首页  
加入 配置
ps：vscode 版本不一样 ，配置的查找是有点不一样
1.40.2 版本 需要 打开后 搜索 eslint 打开 setting 文件
1.25.1 版本 直接 在右侧用户设置里面 配置下方的代码


```
    "eslint.validate": [
        "javascript",
        "javascriptreact",
        {
          "language": "vue",
          "autoFix": true
        },
        "vue"
      ],
      "eslint.autoFixOnSave": true
```
3. 打开就能看到我们之前的那些错误 就可以 在 vscode 中就能有提示

4. 可以将 上述 配置代码直接注释，那么 报错 消失，以此来对比，vscode eslint 插件是否生效

ps：
Vetur 插件是个强大的插件，由于 使用vue 的项目都使用了该插件，那么该插件也是有 vue 的语法提示 功能，和 代码格式化功能（基于prettier），所以很多时候 ，会有误导我们

### vscode 中配置文件的检查配置
```
.eslintignore  给eslint忽略哪些文件
.editorconfig  仅做了解
给编辑器 看的，需要单独安装 编辑器 插件
https://juejin.im/post/5b50269b5188251a9f249ed2
https://www.jianshu.com/p/712cea0ef70e
https://github.com/editorconfig/editorconfig/wiki/EditorConfig-Properties
```


### branch prettier
1. npm install --save-dev prettier


### branch prettierEslit
1. npm install --save-dev eslint-plugin-prettier eslint-config-prettier

2. 此刻 可以将 setting 中 代码检查 单独给 注释 与 影响 看下效果 app.vue 组件，可以看到 prettier 的效果



