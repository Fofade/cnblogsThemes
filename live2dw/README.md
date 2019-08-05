# 关于添加看板娘

因为觉得作者设置的页面左下角的网易云音乐并不实用所以将其改成看板娘

但是由于太菜，不能很好的理解live2d的官方文档

数次度娘都是一些不能用的版本，不是配置少双引号，就是路径错误，看了十几个博客竟没有一个是对的

点进博客根本就没有所谓的看板娘，看页面源码也都是error

几经搜索，终于在一个小时后找到正确配置之法

下面是我的设置，具体代码在html/pageFooter.html
```bash
<!-- 看板娘-->
<script src="https://raw.githubusercontent.com/Fofade/cnblogsThemes/master/live2dw/lib/L2Dwidget.min.js"></script> 
<script src="https://raw.githubusercontent.com/Fofade/cnblogsThemes/master/live2dw/lib/L2Dwidget.0.min.js"></script>
<script>
    L2Dwidget.init({
        "tagMode": false,
        "debug": false,
        "model": {
            "scale": 1,
            "hHeadPos": 0.5,
            "vHeadPos": 0.618,
            "jsonPath": "https://raw.githubusercontent.com/Fofade/cnblogsThemes/master/live2dw/assets/z16.model.json"
        },
        "display": {
            "superSample": 2,
            "width": 150,
            "height": 300,
            "position": "left",
            "hOffset": 0,
            "vOffset": -20
        },
        "mobile": {
            "show": true,
            "scale": 0.5
        },
        "react": {
            "opacityDefault": 0.7,
            "opacityOnHover": 0.2
        }, "log": false
    });</script>
<div id="live2d-widget">
    <canvas id="live2dcanvas" width="200" height="440"
            style="position: fixed; opacity: 1; left: 0px; bottom: 0; z-index: 99999; pointer-events: none;"></canvas>
</div>
```

若自定义只需要将对应的文件链接修改即可

live2dw内的文件是由hexo自动生成的

如果需要换模型最简单的办法是去别人的博客看页面源码，把它的对应链接拷过来！
当然也可以自己生成，建议自己生成！

注意：链接拷贝过来一定要先在浏览器中验证一下