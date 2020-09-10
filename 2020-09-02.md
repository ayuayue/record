处理其他五个模块的错误优化

----

1. 修复因路由定义路由组时导致分页中间件无法正常出发的问题





----

#### 其他

配置` goland ` 的 `go-lint`工具

```go
1. Settings  --> Tools --> External Tools --> +/add

Name : go-lint 

Description : go-lint

Program : $GOPATH/bin/go-lint   # go path 下的bin中
Arguments : $FilePath$ 
Working Directory : $ProjectFileDir$

ok
```

### 使用 `go-land`

1. 单个文件

   右键, External Tools --> go-lint

2. 包

   选中包 右键, External Tools --> go-lint

默认快捷键 : `ctrl + L`