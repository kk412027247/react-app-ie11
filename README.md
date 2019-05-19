> React的脚手架`create-react-app`升级到了`3.0.1`之后，默认在`debug`模式下不支持`IE 11`，如果要支持`IE11`，需要引入第三方依赖包。

###  项目初始化
```
$ npx create-react-app my-app
```

### 兼容`IE11`
1. 安装`core-js`
  
```
$ cd my-app && yarn add core-js
```
2. 在项目入口引入`core-js`。
```
// index.js

import 'core-js';
import React from 'react';
import ReactDOM from 'react-dom';
...
```
4. 修改package.json，删除`development`，改成以下的样子
```
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ]
  }
```

### 在虚拟机/window 子系统开发
在这个环境下，更改文件，网页可能不会刷新。这是要在项目根目录新建`.env`文件，编辑内容。
如果是在window下开发，请直接忽略这个设置。
```
//.env
CHOKIDAR_USEPOLLING=true
```

### 启动项目
```
$ yarn start
```
现在可以在IE11上运行了

> 如果遇到项目还是无法在IE11上启动，请清除一下IE的缓存，或者删除`node_modules`文件夹，重新安装一次。

