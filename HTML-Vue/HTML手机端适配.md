
HTML 手机端适配  
=============
1.代码头部定义
-------------
在`<head>`中引入如下代码  
```
<meta name = "viewport" content="width=device-width,initial-scale=1.0 user-scalable = no , maximum-scale=1.0">
```
2.百分比布局
-------------
百分比布局可以更好的适配网页，如
```
#home-bg{
    width: 100%;
    height: 192px;
}
```
其中`width: 100%;`让图片默认占满整个宽