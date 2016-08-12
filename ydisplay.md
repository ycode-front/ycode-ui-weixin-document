# 展示组件

Ydisplay 这个组件用来将数据转为视图，内部采用Dot模板，可以在配置项中指定数据源。

## Example

数据源

```javascript
{
    "status": 0,
    "message": "success",
    "data": {
        "recordId": 1,
        "receiveNo": "2911733976518",
        "receivePic": null,
        "receiveTime": "2016-05-26 15:22:50",
        "payStatus": 1,
        "receiveStatus": 1,
        "expressName": "快递员1",
        "expressCom": "顺丰快递公司",
        "expressMobile": "18551139364",
        "userName": null,
        "userMobile": null,
        "userNotifyTime": null,
        "userTime": 1464685362000,
        "takePlace":"海德公园"
    },
    "total": 21
}
```

使用

```html
<div
    widget="ydisplay"
    url="/api/getAcceptList.json"
    params--page="1"
    params--size="99999"
>
    <div class="weui_cell">
        <div class="weui_cell_bd weui_cell_primary express-info">
            <div>快递公司：<span>{{=it.expressCom}}</span></div>
            <div>快递到达时间：<span class="receiveTime">{{=it.receiveTime}}</span></div>
            <div>取件地点：<span>{{=it.takePlace}}</span></div>
            <div>取件时间：<span>{{=it.userTime||''}}</span></div>
        </div>
    </div>
</div>
```


## Options

|name|type|required|default|description|
|:---|:---|:---:|:---||
|url|string|yes||数据源地址|
|params|object|no|{}|数据源参数|
|immediately|boolean|no|false|是否在页面加载的时候立即初始化，或者等待手动调用display|
|wait|boolean|no|false|是否显示loading图标|

## Method

### .setParams(params)

设置数据源参数

参数

|name|type|required|default|description|
|:---|:---|:---:|:---||
|params|object|yes| |需要设定的参数|


### .display(data, callback)

对数据进行展示，调用以后会重新获取数据，进行渲染

参数

|name|type|required|default|description|
|:---|:---|:---:|:---||
|data|object or function or null|no| |如果为object,这data作为需要展示的数据，如果为function，则作为处理数据处理器，如果为null，则什么也不做，直接获取数据进行展示|
|callback|function|no| |数据展示完成之后的回调函数|

## Event

|name|target|param|condition|
|:---|:---|:---:|
|ydisplay.displayed|组件本身|{data:data} data为被渲染的数据|在数据展示完成之后调用|
|ydisplay.error|组件本身|response 请求的结果|在数据请求失败之后调用|
