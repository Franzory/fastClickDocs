# fastclick插件使用说明
# a链接在移动端点击后为什么存在延迟？
 从点击屏幕上的元素到触发元素的 click 事件，移动浏览器会有大约 300 毫秒的等待时间。为什么这么设计呢？ 因为它想看看你是不是要进行双击（double tap）操作。
# 引入插件步骤
  ①在HTML页面中添加
    ``<script type='application/javascript' src='/path/to/fastclick.js'></script>  ``
    
注：必须在页面所有Element之前加载脚本文件先实例化fastclick

  ②在JS中添加fastclick的身体，推荐以下做法：
    ``if ('addEventListener' in document) {  
        document.addEventListener('DOMContentLoaded', function() {  
            FastClick.attach(document.body);  
        }, false);  
    } ``
    
  如果你使用了JQuery，那么JS引入就可以改用下面的写法：
   `` $(function() {  
        FastClick.attach(document.body);  
    }); ``
    
  如果你使用Browserify或者其他CommonJS-style 系统,当你调用`require('fastclick')`时，`FastClick.attach`事件会被返回，加载FastClick最简单的方式就是下面的方法了：
   `` var attachFastClick = require('fastclick');  
    attachFastClick(document.body);  ``
