# Demo07


## webpack-dev-server
webpack-dev-server 在 `localhost:8080` 启动一个 express 静态资源 web 服务器，并且会以监听模式自动运行 webpack，在浏览器打开 `http://localhost:8080/` 或 `http://localhost:8080/webpack-dev-server/` 可以浏览项目中的页面和编译后的资源输出，并且通过一个 socket.io 服务实时监听它们的变化并自动刷新页面。

```
# 安装
npm install webpack-dev-server
```

```
webpack-dev-server --progress --colors
```

当本地 8080 端口被占用时，启动服务会报错，此时，我们需要另外制定接口。

```
# port制定端口号
webpack-dev-server --port=3001
```


## 故障处理
Webpack 的配置比较复杂，很容出现错误。我们可以通过参数 `--display-error-details` 来打印错误详情。

```
webpack --display-error-details
```

以上命令执行时，会把异常信息打印出出来。

Webpack 的配置提供了 `resolve` 和 `resolveLoader` 参数来设置模块解析的处理细节，`resolve` 用来配置应用层的模块（要被打包的模块）解析，`resolveLoader` 用来配置 `loader` 模块的解析。

当引入通过 npm 安装的 node.js 模块时，可能出现找不到依赖的错误。Node.js 模块的依赖解析算法很简单，是通过查看模块的每一层父目录中的 `node_modules` 文件夹来查询依赖的。当出现 Node.js 模块依赖查找失败的时候，可以尝试设置 `resolve.fallback` 和 `resolveLoader.fallback` 来解决问题。

```
module.exports = {
  resolve: { fallback: path.join(__dirname, "node_modules") },
  resolveLoader: { fallback: path.join(__dirname, "node_modules") }
};
```