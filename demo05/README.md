# Demo05

将配置项移到配置文件 webpack.config.js 中：
```
module.exports = {
    entry: "./entry.js",
    output: {
        path: __dirname,
        filename: "bundle.js"
    },
    module: {
        loaders: [{
            test: /\.css$/,
            loader: "style!css"
        }]
    }
};
```

然后，执行编译：
```
webpack
```

此时，webpack 会读取 webpack.config.js 中的配置信息进行编译。

当项目复杂度增加时，编译耗时也会增加，此时，在编译时我们可以增加进度查看和颜色显示。
```
webpack --progress --colors
```

在实际项目开发中，可以开启监听模式，避免每次改动模块后都要进行编译。
```
webpack --progress --colors --watch
```