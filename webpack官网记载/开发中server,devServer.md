#### webpack-dev-server 能够用于快速开发应用程序
```
proxy: {
  "/api": {
    target: "http://localhost:3000",
    pathRewrite: {"^/api" : ""}
  }
}

proxy: {
  "/api": "http://localhost:3000"
}
```