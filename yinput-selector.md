# 下拉选择框
yinput-selector 这个组件可指定数据源并渲染下拉选择框，提供触发渲染、修改选择的方法

## Example
数据源
```javascript
{
	"status": 0,
    "data": [{
        "value": 1,
        "alias": "1"
    }, {
        "value": "2",
        "alias": "2"
    }, {
        "value": 3,
        "alias": "3"
    }],
    "message":"success"
}
```
使用
```html
    <select
    class="weui_select tap-blink js-select"
    widget="yinput-selector"
    name="select2"
    placeholder="请选择"
    url="/api/role-selector.json"
    >
    </select>
```
## Options
|name|type|required|default|description|
|:---|:---|:---:|:---||
|url|string|yes||数据源地址|
|params|object|no|{}|数据源参数|
|value|number|no||设置默认选择值|

##Event
|name|target|param|description|
|:---|:---|:---:|:---||
|rendered|组件容器绑定|event|触发事件，渲染完毕|
|input|组件容器绑定|event|触发事件，选项值改变|
