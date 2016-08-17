# 标签切换组件
该组件生成可切换标签
##Example
使用
```html
<div
    class="viewport"
    widget="ytabs"
    tabs=".tab-list li"
    tab-contents=".tab-content"
>
    <ul class="tab-list">
        <li class="active">项脊轩志</li>
        <li>出师表</li>
    </ul>
    <div class="tab-content">
        <article class="weui_article">
            <p>庭有枇杷树，吾妻死之年所手植也，今已亭亭如盖矣。</p>
        </article>
    </div>
    <div class="tab-content">
        <article class="weui_article">
            <p>先帝创业未半而中道崩殂，今天下三分，益州疲弊，此诚危急存亡之秋也。</p>
        </article>
    </div>
</div>
```

##Option
|name|type|required|default|description|
|:---|:---|:---:|:---||
|tabs|string|yes||切换开关|
|tabContents|string|yes||切换的内容|

###参数详细说明

####tabs作为切换开关，需要设置的是切换开关的DOM元素。
####tabContents作为切换的内容，需要设置包含内容的DOM元素。

-该两项设置为必须，组件内部根据设置项渲染模板，对于设直项的DOM结构参照给出的Example。

##Methods
###.enableTab()
让设置的tab开关起作用


