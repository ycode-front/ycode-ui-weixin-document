# 搜索组件

表现为一个搜索框，可以指定搜索的数据源。点击后跳转到搜索界面，输入关键字点击搜索之后，展示搜索结果。支持本地搜索和远程搜索

## Example

```html
<div class="js-search"></div>
```

```javascript
$('.search1').ysearch({
    placeholder: 'pleace search',
    templateFn: function(data) {
        return '<p>' + data.name + ' age:' + data.age + '</p>';
    },
    dataSource: '/api/ysearch-demo.json',
    remote: true
});
```

## Options

|name|type|required|default|description|
|:---|:---|:---:|:---||
|remote|boolean|no|false|是否进行远程搜索|
|dataSource|array or string|no|''|当remote 为 true的时候， 进行远程搜索， dataSource指定远程搜索的数据源，反之，dataSource 指定本地数据源，也就是数据本身|
|params|object|no|{}|如果为远程搜索，则params指定数据源的参数|
|targets|array|no|[]|搜索的目标，也就是 dataSource 中数据项中被搜索的属性,可以指定多个|
|templateFn|function|no||搜索项的模板函数 传入数据，返回渲染之后的字符串，见详情|
|placeholder|string|no|'搜素'|搜索框占位符|
|keywordKey|string|no|'keyword'|指定搜索关键字的key值|

### 参数详细说明

#### templateFn

这是一个回调函数，传入搜索结果的item，返回渲染之后的字符串

example

```javascript
{
    ...
    templateFn:function(data) {
        return '<p>' + data.name + ' age:' + data.age + '</p>';
    }
    ...
}
```



## Methods

### .setDataSource(dataSource)

设置数据源

参数

|name|type|required|default|description|
|:---|:---|:---:|:---||
|dataSource|string or array|yes| |数据源，可以是数据本身也可以是远程数据url|

### .setParams(params)

设置数据源参数，只有在远程搜索的时候，采用对象扩展的方式

参数

|name|type|required|default|description|
|:---|:---|:---:|:---||
|params|object|yes| |数据源参数|

### .cancel()

取消搜索，退出搜索界面

## Events

|name|target|param|condition|
|:---|:---|:---:|:---:|
|selected|组件本身|搜索结果中被选中的 条目的数据|再选中搜索结果数据的时候触发|
