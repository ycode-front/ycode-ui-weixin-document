# 表单组件

表单组件用来代理表单的提交，相对于直接表单提交，使用表单提交提供了一下的好处

- 采用异步提交，从而可以对表单提交之后的结果进行处理
- 对提交结果处理实现了部分自动化，统一交互，减少代码
- 对重复提交做了预防
- 文件上传过程中做了禁止提交处理

## Example

```html
<form
    widget="yform"
    action="/weixin/address/save"
    submit-button=".js-submit"
    auto="true"
    redirect="{back}"
    message--0="地址添加成功"
>
    <input type="text" name="name" />
    <input type="submit" class="js-submit" />
</form>
```

## Options

|name|type|required|default|description|
|:---|:---|:---:|:---||
|action|string|yes||表单提交的url|
|submitButton|string|no|''|指定提交按钮，可以为jquery查询语句，也可以是jquery对象|
|direct|boolean|no|false|是否直接进行提交|
|success|function|no||回调函数，在提交表单成功之后调用，无论 status 为多少都算成功|
|error|boolean|no||回调函数，在表单提交失败之后调用|
|auto|boolean|no|false|是否代理处理表单的提交结果|
|message|object|no|false|用来指定 status 和 需要提示的message的匹配信息，如果没有设置，则会按照后台message进行提示，配置详情见下面的说明|
|redirect|string|no||提交成功之后，页面跳转的地址，这里的提交成功是指 status==0|

### 参数详细说明

#### auto 代理处理返回结果

auto为true的时候，会出现如下效果

- 如果表单提交返回的结果 status 不等于 0，则自动 alert message 信息
- 如果指定了 redirect，则提交成功 并且 status 等于 0 的时候，页面会自动跳转到 redirect 指定的地址

#### message 指定提示语

message 是一个对象，或者一个map，key 为 status 的值，value 为提示文案

```javascript
message: {
    0:"提交成功",
    1:"失败了",
    2:"另一种失败"
}
```


## Methods

### .setAction(action)

设置表单提交的目标

参数

|name|type|required|default|description|
|:---|:---|:---:|:---||
|action|string|yes| |需要设定的表单提交目标|


## Events

|name|target|param|condition|
|:---|:---|:---:|
|yform.success|组件本身|response 请求的结果，第二个参数 request 请求的参数|在表单提交成功之后调用|
|yform.error|组件本身|response 请求的结果|在表单提交失败之后调用|