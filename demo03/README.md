# Demo03

webpack 生来只能处理 javasript，所以我们需要 `css-loader` 来处理 css 文件，同时需要 `style-loader` 来执行其中的样式。

安装依赖：
```
npm install css-loader style-loader
```

安装完成后，会在根目录下生成 node_modules 目录，其中包含依赖文件。

执行编译：
```
webpack entry.js bundle.js
```

编译后，entry.js 中引用的 style.css 会编译打包到 bundle.js 中。