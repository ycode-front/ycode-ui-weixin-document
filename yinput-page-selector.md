# 跳转选择页

点击跳转到一个页内页进行选择，选择完成之后，返回当前页面。并且在本页面显示刚才所选

同时组件提供如下功能

- 搜索
- 建议
- 禁用部分选项
- 选项按照首字母分组
- 代理选中行为

## Example

数据源 /api/getAllCity.json
```json
{
    "status": 0,
    "message": "success",
    "data": [{
        "value": "3205",
        "alias": "苏州市"
    },{
        "value": "3206",
        "alias": "湖州市"
    }],
    "total": 0
}
```

使用
```html
<!-- 用来显示选择的值 -->
<input
    type="text"
    readonly="readonly"
    class="weui_input js-page-selector-show"
    placeholder="请选择市"
/>
<!-- 用来存储实际提交的值 -->
<input
    type="hidden"
    class="js-page-selector"
    widget="yinput-page-selector"
    title="请选择市"
    value=""
    data-source--url="/api/getAllCity.json"
    trigger=".js-page-selector-show"
    display-as-value=".js-page-selector-show"
/>
```

## Options

|name|type|required|default|description|
|:---|:---|:---:|:---||
|dataSource|Object|yes||关于数据源的配置项|
|dataSource.url|string|yes||数据源的url|
|dataSource.params|Object|no|{}|数据源的url参数|
|dataSource.template|function|no|默认模板|数据源匹配的模板，**见详情**|
|dataSource.searchTemplate|function|no|默认模板|搜索功能搜索的结果模板|
|dataSource.displayKey|string|no|'alias'|选择之后展示出来的字段名|
|dataSource.valueKey|string|no|'value'|选择之后作为作为value提交的字段名|
|title|string|no|''|在选择页面头部显示的title|
|searchable|boolean|no|false|是否启动搜索组件|
|suggest|object|no|默认的建议配置|用来配置选项建议的内容|
|suggest.data|array|no|[]|建议的条目的数据|
|suggest.title|string|no|'建议'|建议的小标题，显示在建议区域的左上角|
|suggest.template|function|no|默认模板|建议数据显示的模板，**见详情**|
|suggest.valueKey|string|no|'value'|建议数据中作为value提交的字段名|
|groupByInitial|boolean|no|false|是否将选项用首字母分割|
|value|string|no|''|input的值|
|trigger|string|no|''|制定一个元素，作为选择页面的展示的触发器，默认情况下组件本身就是触发器|
|display|string|no|''|指定显示的元素|
|displayAsValue|string|no|''|指定显示的元素,和display不同的是，显示的内容将作为指定元素的 value属性，通常指定的元素是input|
|disabledCondition|function|no|默认条件为false|一个回调函数，决定何时选择项是禁用的，**见详情**|
|disabledClass|string|no|''|当选择项为disabled状态的时候的class值，**见详情**|
|agentCondition|function|no|默认条件为false|一个回调函数，决定何时点击选项时候的组件行为需要被重新定义，**见详情**|
|agentCallback|function|no|默认回调不使用进行任何操作|回调函数，在定义agentCondition的情况下，点击满足条件的选项会调用此回调函数，**见详情**|


### 选项详情

#### dataSource.template

这个选项是一个回调函数，返回值作为显示的模板，传入两个参数

- itemData [object]单个选项的数据 
- selected [boolean] 当前是否被选中

#### suggest.template

这个选项是一个回调函数，返回值作为显示的模板，传入一个参数

- itemData [object]单个选项的数据 

#### disabledCondition

回调函数，返回值作为选项是否disabled的结果，传入一个参数

- itemData [object]单个选项的数据 

#### agentCondition

回调函数，返回值作为选项是否进行选中后自定义行为的结果，传入一个参数

- itemData [object]单个选项的数据 

## Methods

### .getParams(callback)

用来获取组件的url参数

|name|type|required|default|description|
|:---|:---|:---:|:---||
|callback|string|yes| |用来接收返回的结果|

### .initPreValue()

初始化预设值，如果改变了value值，组件里面的状态不会主动同步，需要调用这个函数

### .set(key, value)

设置组件里面任何的选项

example
```javascript
$(...).yinputPageSelector().set('dataSource.params', {code: 321});
```

### .sync()

同步组件内部的状态，一般在外部改变了组件的状态的时候进行调用

## Events

|name|target|param|condition|
|:---|:---|:---|:---|
|yinputPageSelector.sync|组件本身||在组件进行数据同步的时候调用， 也就是请求数据的时候调用|
|yinputPageSelector.selected|组件本身|optionData 被选中的选项数据|点击某个选项的时候调用，如果选项被代理了， 则不会触发|
|yinputPageSelector.rendered|组件本身||在每次渲染完成之后调用|
|yinputPageSelector.forward|组件本身||页面切换开始的时候调用|
|yinputPageSelector.forwarded|组件本身||页面切换结束的时候调用|
|yinputPageSelector.back|组件本身||页面返回开始的时候调用|
|yinputPageSelector.backed|组件本身||页面返回结束的时候调用|
