# Demo02

编译文件：
```
webpack entry.js bundle.js
```

其中，entry.js 中依赖了 content.js 文件。

webpack 会分析 entry.js 中的依赖，并将这些依赖文件全部打包编译到 bundle.js 中。