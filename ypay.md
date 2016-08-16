# 支付按钮组件

初始化组件

## Example

```html
<a 
    class="weui_btn js-pay" 
    href="javascript:;"
    widget="ypay"
    debug="false"
    url="/weixin/garbageFees/pay"
>立即支付</a>
```

## Options

|name|type|required|default|description|
|:---|:---|:---:|:---||
|url|string|yes||获取支付信息的url|
|params|object|no|{}|获取支付信息的url参数|
|message.success|string|no|'支付成功'|支付成功之后的提示信息|
|debug|boolean|no|false|是否启用debug模式，debug模式下，会alert出支付过程中每一步的信息|

## Methods

### .setParams(params)

设置数据源参数

参数

|name|type|required|default|description|
|:---|:---|:---:|:---||
|params|object|yes| |需要设定的参数|


## Events

|name|target|param|condition|
|:---|:---|:---:|:---:|
|ypay.success|组件本身||再支付成功之后调用|
|ypay.error|组件本身||再支付失败之后调用|