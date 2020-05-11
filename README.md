沃尔玛商家数据平台
===========================


## 项目背景
在数据平台中，根据沃尔玛侧提出的品类分析需求，定制化设计，个别模块后续可能通用于其他商家


## 项目环境
* 脚手架版本- @vue/cli 4.3.1
* node版本 - v12.4.0
* npm版本 - v6.9.0

## src 目录结构

```sh
├── package.json
├── public
│   ├── favicon.ico
│   └── index.html
├── src
│   ├── App.css
│   ├── App.js
│   ├── App.test.js
│   ├── index.css
│   ├── index.js
│   └── logo.svg
└── yarn.lock
```


## 命名规范

引用规范
* 脚本引入不加后缀 .js
* 组件引入不加后缀 .vue
* 资源引入请使用 @ 符
* 引入 index.js时 ，默认'不加文件名'，如：'@/src/views/order'

```sh
├── public
│   ├── static（第三方静态依赖资源）
│   ├── index.html
│   │ 
├── src
│   ├── dada 「达达组件库」
│   │   └── componens （组件库）
│   │       └── table（命名小写，尽量用'单词'形容，或者用 '-'）
│   │           └── demo（使用实例）
│   │           └── src（统一文件名）
│   │               └── table.vue（功能组件）
│   │           └── index.js（挂载）
│   │       └── index.js（挂载）
|   |
│   │   └── assets （静态库）
│   │       └── css （样式）
│   │           └── common
│   │               └── table.css （组件样式）
│   │           └── index.css （样式入口）
│   │       └── images （图片）
|   |
│   │   └── lib（逻辑库）
│   │       └── utils（工具）
│   │           └── index.js
│   │       └── directives（指令）
│   │           └── index.js
│   │       └── filters（过滤）
│   │           └── index.js
│   │       └── enums（枚举）
│   │           └── index.js
│   │       └── mixins（混入）
│   │           └── table.js // 混入脚本，以功能命名
|   |
│   │   └── examples（实例库）
│   │
│   │   └── docs（使用说明.md）
|   |
|   |   ******************************
|   |
|   |
│   ├── components 「项目私有组件」
│   │   └── menu （尽量用'单词'形容，或者用 '-'）
│   │       └── menu.vue
│   │
│   ├── api（接口库）
│   │
│   ├── assets（静态库）
│   │
│   ├── lib（逻辑库）
│   │   └── utils（工具）
│   |       └── index.js
│   │   └── directives（指令）
│   |       └──  index.js
│   │   └── filters（过滤）
│   |       └── index.js
│   │   └── enums（枚举）
│   |       └──  index.js
│   │   └── mixins（混入）
│   |       └──  table.js // 混入脚本，以功能命名
│   │
│   ├── store 「vuex」
│   │   └── getters.js
│   │   └── actions.js
│   │   └── mutations-types.js
│   │   └── mutations.js
│   │   └── store.js
│   │
│   ├── router 「路由文件」
│   │   └── index.js
│   │   └── config.js
│   │
│   └── views 「页面」
│       └── order （一级命名 用'单词'形容）
│           └── components （页面级组件）
│           └── index.js （引入时默认'不加文件名'，如：'@/src/views/order' 即可）
│           └── Edit.js （驼峰命名，编辑or修改，就用此命名）
├──         └── Detail.js （驼峰命名，详情页or查看页，就用此命名）





```
> 注： 各导航目录及文件  的名称尽量与路由的名称对应

## Git flow 规范

```sh
* **master 分支**：对应线上（正式环境）的代码，一旦版本上线由测试人员发送合并matser邮件，开发人员将对应上线tag版本合并至master分支。

* **testing 分支**：预发布分支，等待被整合到 master 分支中。在测试通过后需要上线时，将该分支合入到 master 分支上。

* **develop 分支**：用于新需求（版本）开发,永远是功能最新最全的分支

* **feature 分支**：开发新功能时，需要从 dev 分支上拉取新分支，新分支的命名规则中必须加入创建者的名字缩写，例如：**feature/LJ-xxx**。

* **hotfix 分支**：当 master 分支上出现 bug 时，使用该分支。命名规则同 dev 分支。
  **注意: hotfix 合入 master 分支之后，立即完成 master 分支的 tag 操作**。

* **提交 commit**：尽量详细写明提交的内容。

```

## 注解规范
```javascript
 /**
 * 日期 周/月 格式处理
 * @param {string} val 日期 2020-1-1
 * @param {string} type 转换类型 week/ month
 * @returns {string} 2020W01/2020M01
 */
```

### Vue组件中函数的先后顺序

>jsx 编写顺序为：proptype , constructor， 生命周期，自定义方法，具体可参考Eslint中sort-comp规范
>自我约束，强制组件方法顺序

```vue


```


## 代码规范

项目使用 `ESLint` 进行代码风格规范，使用 [babel-eslint](https://developer.aliyun.com/mirror/npm/package/babel-eslint) 为基本标准，在这基础上做了定制
1. vscode 安装一下插件
    >EsLint、vetur
2. vscode设置了添加配置项，默认会去查找你项目中的eslint配置文件
```
    {
       // "eslint.autoFixOnSave": true,  // 启用保存时自动修复,默认只支持.js文件 [个人建议关闭此功能，自行约束个人编码规范]
       "eslint.validate": [
           "javascript",
           "javascriptreact",
           "html",
           "vue"
       ]
    }
```
ps: 仅供参考，可用其他方式

```ESLint
  rules: {
    "no-console": process.env.NODE_ENV === "production" ? 2 : 0,// 允许在开发环境下使用console
    "no-debugger": process.env.NODE_ENV === "production" ? 2 : 0,// 允许在开发环境下使用debugger
    "no-alert": 0,//禁止使用alert confirm prompt
    "no-array-constructor": 2,//禁止使用数组构造器
    "no-bitwise": 0,//禁止使用按位运算符
    "no-caller": 1,//禁止使用arguments.caller或arguments.callee
    "no-catch-shadow": 2,//禁止catch子句参数与外部作用域变量同名
    "no-class-assign": 2,//禁止给类赋值
    "no-cond-assign": 2,//禁止在条件表达式中使用赋值语句
    "no-const-assign": 2,//禁止修改const声明的变量
    "no-constant-condition": 2,//禁止在条件中使用常量表达式 if(true) if(1)
    "no-continue": 0,//禁止使用continue
    "no-control-regex": 2,//禁止在正则表达式中使用控制字符
    "no-delete-var": 2,//不能对var声明的变量使用delete操作符
    "no-div-regex": 1,//不能使用看起来像除法的正则表达式/=foo/
    "no-dupe-keys": 2,//在创建对象字面量时不允许键重复 {a:1,a:1}
    "no-dupe-args": 2,//函数参数不能重复
    "no-duplicate-case": 2,//switch中的case标签不能重复
    "no-else-return": 2,//如果if语句里面有return,后面不能跟else语句
    "no-empty": 2,//块语句中的内容不能为空
    "no-empty-character-class": 2,//正则表达式中的[]内容不能为空
    "no-eq-null": 2,//禁止对null使用==或!=运算符
    "no-eval": 1,//禁止使用eval
    "no-ex-assign": 2,//禁止给catch语句中的异常参数赋值
    "no-extend-native": 2,//禁止扩展native对象
    "no-extra-bind": 2,//禁止不必要的函数绑定
    "no-extra-boolean-cast": 2,//禁止不必要的bool转换
    "no-extra-parens": 2,//禁止非必要的括号
    "no-extra-semi": 2,//禁止多余的冒号
    "no-fallthrough": 1,//禁止switch穿透
    "no-floating-decimal": 2,//禁止省略浮点数中的0 .5 3.
    "no-func-assign": 2,//禁止重复的函数声明
    "no-implicit-coercion": 1,//禁止隐式转换
    "no-implied-eval": 2,//禁止使用隐式eval
    "no-inline-comments": 0,//禁止行内备注
    "no-inner-declarations": [2, "functions"],//禁止在块语句中使用声明（变量或函数）
    "no-invalid-regexp": 2,//禁止无效的正则表达式
    "no-irregular-whitespace": 2,//不能有不规则的空格
    "no-iterator": 2,//禁止使用__iterator__ 属性
    "no-label-var": 2,//label名不能与var声明的变量名相同
    "no-labels": 2,//禁止标签声明
    "no-lone-blocks": 2,//禁止不必要的嵌套块
    "no-lonely-if": 2,//禁止else语句内只有if语句
    "no-loop-func": 1,//禁止在循环中使用函数（如果没有引用外部变量不形成闭包就可以）
    "no-mixed-requires": [0, false],//声明时不能混用声明类型
    "linebreak-style": [0, "windows"],//换行风格
    "no-multi-spaces": 1,//不能用多余的空格
    "no-multi-str": 2,//字符串不能用\换行
    "no-multiple-empty-lines": [1, { "max": 2 }],//空行最多不能超过2行
    "no-native-reassign": 2,//不能重写native对象
    "no-negated-in-lhs": 2,//in 操作符的左边不能有!
    "no-nested-ternary": 0,//禁止使用嵌套的三目运算
    "no-new": 1,//禁止在使用new构造一个实例后不赋值
    "no-new-func": 1,//禁止使用new Function
    "no-new-object": 2,//禁止使用new Object()
    "no-new-require": 2,//禁止使用new require
    "no-new-wrappers": 2,//禁止使用new创建包装实例，new String new Boolean new Number
    "no-obj-calls": 2,//不能调用内置的全局对象，比如Math() JSON()
    "no-octal": 2,//禁止使用八进制数字
    "no-octal-escape": 2,//禁止使用八进制转义序列
    "no-param-reassign": 2,//禁止给参数重新赋值
    "no-path-concat": 0,//node中不能使用__dirname或__filename做路径拼接
    "no-plusplus": 0,//禁止使用++，--
    "no-process-env": 0,//禁止使用process.env
    "no-process-exit": 0,//禁止使用process.exit()
    "no-proto": 2,//禁止使用__proto__属性
    "no-redeclare": 2,//禁止重复声明变量
    "no-regex-spaces": 2,//禁止在正则表达式字面量中使用多个空格 /foo bar/
    "no-restricted-modules": 0,//如果禁用了指定模块，使用就会报错
    "no-return-assign": 1,//return 语句中不能有赋值表达式
    "no-script-url": 0,//禁止使用javascript:void(0)
    "no-self-compare": 2,//不能比较自身
    "no-sequences": 0,//禁止使用逗号运算符
    "no-shadow": 0,//外部作用域中的变量不能与它所包含的作用域中的变量或参数同名
    "no-shadow-restricted-names": 2,//严格模式中规定的限制标识符不能作为声明时的变量名使用
    "no-spaced-func": 2,//函数调用时 函数名与()之间不能有空格
    "no-sparse-arrays": 2,//禁止稀疏数组， [1,,2]
    "no-sync": 0,//nodejs 禁止同步方法
    "no-ternary": 0,//禁止使用三目运算符
    "no-trailing-spaces": 1,//一行结束后面不要有空格
    "no-this-before-super": 0,//在调用super()之前不能使用this或super
    "no-throw-literal": 2,//禁止抛出字面量错误 throw "error";
    "no-undef": 1,//不能有未定义的变量
    "no-undef-init": 2,//变量初始化时不能直接给它赋值为undefined
    "no-undefined": 2,//不能使用undefined
    "no-unexpected-multiline": 2,//避免多行表达式
    "no-underscore-dangle": 1,//标识符不能以_开头或结尾
    "no-unneeded-ternary": 2,//禁止不必要的嵌套 var isYes = answer === 1 ? true : false;
    "no-unreachable": 2,//不能有无法执行的代码
    "no-unused-expressions": 2,//禁止无用的表达式
    "no-use-before-define": 2,//未定义前不能使用
    "no-useless-call": 2,//禁止不必要的call和apply
    "no-var": 0,//禁用var，用let和const代替
    "no-warning-comments": [1, { "terms": ["todo", "fixme", "xxx"], "location": "start" }],//不能有警告备注
    "no-with": 2,//禁用with
    "array-bracket-spacing": [2, "never"],//是否允许非空数组里面有多余的空格
    "arrow-parens": 0,//箭头函数用小括号括起来
    "arrow-spacing": 0,//=>的前/后括号
    "accessor-pairs": 0,//在对象中使用getter/setter
    "block-scoped-var": 0,//块语句中使用var
    "brace-style": [1, "1tbs"],//大括号风格
    "callback-return": 1,//避免多次调用回调什么的
    "camelcase": 2,//强制驼峰法命名
    "comma-dangle": [2, "never"],//对象字面量项尾不能有逗号
    "comma-spacing": 0,//逗号前后的空格
    "comma-style": [2, "last"],//逗号风格，换行时在行首还是行尾
    "complexity": [0, 11],//循环复杂度
    "computed-property-spacing": [0, "never"],//是否允许计算后的键名什么的
    "consistent-return": 0,//return 后面是否允许省略
    "consistent-this": [0, "that"],//this别名
    "constructor-super": 0,//非派生类不能调用super，派生类必须调用super
    "dot-location": 0,//对象访问符的位置，换行的时候在行首还是行尾
    "dot-notation": [0, { "allowKeywords": true }],//避免不必要的方括号
    "eol-last": 0,//文件以单一的换行符结束
    "eqeqeq": 2,//必须使用全等
    "func-names": 0,//函数表达式必须有名字
    "func-style": [0, "declaration"],//函数风格，规定只能使用函数声明/函数表达式
    "generator-star-spacing": 0,//生成器函数*的前后空格
    "guard-for-in": 0,//for in循环要用if语句过滤
    "handle-callback-err": 0,//nodejs 处理错误
    "id-length": 0,//变量名长度
    "indent": [2, 4],//缩进风格
    "init-declarations": 0,//声明时必须赋初值
    "key-spacing": [2, { "beforeColon": false, "afterColon": true }],//对象字面量中冒号的前后空格
    "lines-around-comment": 0,//行前/行后备注
    "max-statements": [0, 10],//函数内最多有几个声明
    "new-cap": 2,//函数名首行大写必须使用new方式调用，首行小写必须用不带new方式调用
    "new-parens": 2,//new时必须加小括号
    "object-curly-spacing": [0, "never"],//大括号内是否允许不必要的空格
    "object-shorthand": 0,//强制对象字面量缩写语法
    "one-var": 1,//连续声明
    "operator-assignment": [0, "always"],//赋值运算符 += -=什么的
    "operator-linebreak": [2, "after"],//换行时运算符在行尾还是行首
    "padded-blocks": 0,//块语句内行首行尾是否要空行
    "prefer-const": 0,//首选const
    "prefer-spread": 0,//首选展开运算
    "prefer-reflect": 0,//首选Reflect的方法
    "radix": 2,//parseInt必须指定第二个参数
    "id-match": 0,//命名检测
    "require-yield": 0,//生成器函数必须有yield
    "semi": [2, "always"],//语句强制分号结尾
    "semi-spacing": [0, { "before": false, "after": true }],//分号前后空格
    "sort-vars": 0,//变量声明时排序
    "space-after-keywords": [0, "always"],//关键字后面是否要空一格
    "space-before-blocks": [0, "always"],//不以新行开始的块{前面要不要有空格
    "space-before-function-paren": [2, "never"],// 不允许函数与括号之前有空格
    "space-infix-ops": 0,//中缀操作符周围要不要有空格
    "space-return-throw-case": 0,//return throw case后面要不要加空格
    "space-unary-ops": [0, { "words": true, "nonwords": true }],//一元运算符的前/后要不要加空格
    "spaced-comment": 2,//注释风格要有空格什么的
    "strict": 2,//使用严格模式
    "use-isnan": 2,//禁止比较时使用NaN，只能用isNaN()
    "valid-jsdoc": 0,//jsdoc规则
    "valid-typeof": 2,//必须使用合法的typeof的值
    "vars-on-top": 0,//var必须放在作用域顶部
    "wrap-iife": [2, "inside"],//立即执行函数表达式的小括号风格
    "wrap-regex": 0,//正则表达式字面量用小括号包起来
    "yoda": [2, "never"],//禁止尤达条件
    "radix": 0,
    "no-undef": 0,
    "vue/no-use-v-if-with-v-for": [0],
    "keyword-spacing": [2],// 关键字前后不加空格
    "indent": ["error", 2, { "SwitchCase": 1 }], // @fixable jsx 的 children 缩进必须为四个空格
    "no-proto": 0, // 禁止使用 __proto__
    "one-var": [2, { const: "never" }], //是否允许使用逗号一次声明多个变量  所有 const 声明必须独占一行，不允许用逗号定义多个
    "no-extra-boolean-cast": 0,// 允许双重否定
    'eol-last': 2,//这句话表示在文件末尾可以不加回车
    "no-unused-vars": [2,// 禁止定义不使用的变量
      {
        vars: "all", // 变量定义必须被使用
        args: "none", // 对于函数形参不检测
        ignoreRestSiblings: true, // 忽略剩余子项 fn(...args)，{a, b, ...coords}
        caughtErrors: "none" // 忽略 catch 语句的参数使用
      }
    ]
  }
```


```

### Plan

```js
- [ ] 1. 

- [x] 2. 
```
