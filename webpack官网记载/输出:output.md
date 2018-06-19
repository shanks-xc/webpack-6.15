> 输出output(即使有多个入口点，也只能有一个输出)
* filename:文件名
* path:绝对路径
> 多个入口起点的话 应该用以下写法，保证唯一性
```
{
  entry: {
    app: './src/app.js',
    search: './src/search.js'
  },
  output: {
    filename: '[name].js',
    path: __dirname + '/dist'
  }
}
```

