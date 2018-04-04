# 快速开始

## 下载

imgAutoSize (当前版本 v1.0.0) Demo及文件集成包下载地址

> [ https://github.com/ailewl/imgAutoSize/](https://github.com/ailewl/imgAutoSize/)

## 包含的内容
集成包内包含：
```text
└── demo
    ├──index.html             [不必要的html文件，演示使用]
    └── scripts
         ├── imgAutoSize.js       [此插件开发版本]
         └── imgAutoSize.min.js   [此插件压缩版本]
```

# 介绍

## imgAutoSize 是什么

<p class="tip">
    imgAutoSize是一个纯原生js的超轻量级图片自适应插件，不依赖任何库运行
</p>

## 作用

<p class="warn">
    将图片以父级框架根据图片焦点位置自适应放大
</p>

# 起步

## 基本模板

>使用以下给出的这份超级简单的 HTML 模版，或者修改这些实例。我们强烈建议你对这些实例按照自己的需求进行修改，而不要简单的复制、粘贴。

###  引入

<p class="tip">
    我们推荐在开发时使用开发版本(<code>imgAutoSize.js</code>)，在发布时使用压缩版本(<code> imgAutoSize.min.js </code>)
</p>

```html
        <!--引入插件js文件-->
        <script src="scripts/imgAutoSize.js" type="text/javascript" charset="utf-8"></script>
```


### 基本布局

```html
    <div class="container">
        <div class="imgbox">
            <img src="demo.jpg" alt="" />
        </div>
        <div class="imgbox">
            <img src="demo.jpg" alt="" />
        </div>
        <div class="imgbox">
            <img src="demo.jpg" alt="" />
        </div>
    </div>
```
    *   限制图片大小及位置
        *   用来包含图片图片容器
            *   图片1
        *   用来包含图片图片容器
            *   图片2
        *   用来包含图片图片容器
            *   图片3

## 使用

### 获取所需数据

>   1. 确定图片 ``焦点``位置[图片显示的重心点]
>   2. 获取图片父级节点[包含图片容器的节点]

### 配置插件

```javascript
    window.onload = function(){
        var imgDad = document.getElementsByClass('imgbox')[0];
        new imgAutoSize({
            imgbox:imgDad,//图片容器
            Left:200,//图片焦点到图片左侧的距离
            Top:200,//图片焦点到图片顶部的距离
            window:false//是否以浏览器窗口大小为图片大小
        })
    }
```
### 配置项

<p class="tip">
    参数以json格式传入，无默认值的为必要参数
</p>
#### imgbox
- 类型： `Dom对象`
- 默认值： `无`

图片的父级容器，会自动加载必要的样式

```javascript

    new imgAutoSize({
        imgbox:document.getElementById('ImgBox')
    })

```

#### Left
- 类型： `Number`
- 默认值： `图片原始宽度的一半`

图片焦点到图片左侧的距离，无需单位

```javascript

    new imgAutoSize({
        Left:200
    })

```

#### Top
- 类型： `Number`
- 默认值： `图片原始高度的一半`

图片焦点到图片顶部的距离，无需单位

```javascript

    new imgAutoSize({
        Top:400
    })

```

#### window
- 类型： `Boolean`
- 默认值： `false`

图片是否全屏显示，以浏览器窗口为父级

```javascript

    new imgAutoSize({
        window:true
    })

```
