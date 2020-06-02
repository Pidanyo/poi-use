# PoiDemo
springboot项目上传下载excel，并通过poi把对应数据导入导出到数据库中

使用`Workbook wb = WorkbookFactory.create(inp);`
用这种方法创建Workbook可以使解析上传的excel同时兼容xls、xlsx两种格式

处理火狐和Safari浏览器 中文文件名乱码：

```
response.setHeader("Content-Disposition", "attachment; filename=\"" + fileName + "\"; filename*=utf-8''" + fileName);
```

该版本 去除了一些不必要的代码 以及 依赖 简单做了一小部分优化，其次在导出Excel的时候 加了两个创建Style的方法 （getColumnTopStyle，getStyle）前者是设置第一行标题的样式 后者是设置其他行的样式

本方法参照了 https://blog.csdn.net/qq_40543150/article/details/103522856

使用方法可以对比参照（由于只是整理学习知识点，并未进行更改。）



注意事项：在数据库内容较多的时候  （测试数据大于500）在导出Excel的时候会出现空指针的异常。暂时还未找到解决办法