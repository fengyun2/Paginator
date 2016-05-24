# 这是一个基于bootstrap和jquery的分页插件

### USAGE

1. 引入三个文件
分别是 bootstrap.css, jquery.js, paginator.js
```html
  <link rel="stylesheet" type="text/css" href="../css/bootstrap.min.css">
  <script type="text/javascript" src="../js/jquery.min.js"></script>
  <script type="text/javascript" src="../js/bootstrap-paginator.js"></script>
```

2. 调用

```js
// 显示分页
var options = {
  bootstrapMajorVersion: 3, //版本[这里必须选择版本3]
  currentPage: app.cur_page, //当前页数
  totalPages: app.page_count, //总页数
  itemTexts: function (type, page, current) {
    switch (type) {
      case "first":
      return "首页";
      case "prev":
      return "上一页";
      case "next":
      return "下一页";
      case "last":
      return "末页";
      case "page":
      return page;
    }
  },//点击事件，用于通过Ajax来刷新整个list列表
  onPageClicked: function (event, originalEvent, type, page) {
    app.cur_page = page;
  }
};
app.dom.page_list.bootstrapPaginator(options);
```

### careful
`app.dom.page_list`: 必须是jquery节点
