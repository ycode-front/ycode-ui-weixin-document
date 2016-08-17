# 表单校验组件
yvalidate这个组件用来校验表单

## Example

使用

```html
<input
    class="weui_input"
    type="phone"
    maxlength="11"
    placeholder="请输入qq号"
    name="qq"
    widget="yvalidate"
    rules--0--rule="required"
    rules--0--message="请输入手机号码"
    rules--1--rule="phone"
    rules--1--message="请输入正确的手机号码"
>
```
## Options

|name|type|required|default|description|
|:---|:---|:---|:---|:---|
|type|string|no||原生input属性，指定类别|
|maxlength|number|no||原生input属性，指定输入最大长度|
|placeholder|string|no||原生input属性，指定输入框的默认值|
|rules--(0-5)--rule|string|no|pass|组件的校验类型，可选值有required、email、phone、pass、checked、creditcard、password|
|rules--(0-5)--message|string|no|''|校验不通过时的提示信息，以弹窗的形式提示|

## Method

### .enable()

让当前的校验器生效

### .disable()

让当前的校验器失效
