# Demo04

首先，安装依赖：
```
npm install css-loader style-loader
```

在 entry.js 中，我不想写这么长的引用 `require("!style!css!./style.css");`。

精简引入方式：
```
require("./style.css");
```

此时，我们需要绑定文件扩展到编译命令中：
```
webpack ./entry.js bundle.js --module-bind 'css=style!css'
```