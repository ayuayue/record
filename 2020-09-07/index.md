### 测试编写
1. 使用 `buffalo suite` 测试套件,使用` buffalo test packageName -m handleName` 进行测试,每次只运行一个测试,在`github`上提了一个 `issues`
2. 使用 ` goland ` 的测试方式,可以进行正常的测试
3. 使用 `go test ` 命令也有些问题

最后使用 2 进行测试的运行.

### 序列号绑定设备
1. 创建关联表,记录序列号与设备uid
2. 编辑及删除操作的完善

### 设备创建时优化
优化一些下拉框为` ajax` 的方式进行交互.