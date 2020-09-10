1. `echart` 初始化问题

   1. 版本问题,更换版本既可以初始化

2. 接口数据的更改

   1. 取消返回的` value` 属性

3. 渲染完成后的事件监听

   1. 点击事件 

      ​	点击跳转到对应的对象的详情页

   2. 鼠标右键点击

      ​	点击弹框,询问受否解除关联  --使用 `layui use layer`

4. 阻止`html` 特定对象的右键菜单,避免影响视图的右键事件

   ```java
   obj.oncontextmenu = function(){
       return false;
   }
   ```

   

