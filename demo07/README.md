# Demo07

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