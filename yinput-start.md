# 星级展示选择 

yinput-start组件可用来展示星级且可以编辑星级(点击进行星级编辑)

##Example

使用
```html
	<input
        widget="yinput-star"
        number="5"
        name="star"
        value="4"
        readonly="true"
    />
```

##Option 

|name|type|required|default|description|
|:---|:---|:---:|:---||
|number|number|yes||设置星星数量|
|value|number|no||设置默认选择星级数|
|readonly|boolean|no|false|是否可编辑星级数|


##Methods
### .renderStart(starN)

渲染星星数据

参数

|name|type|required|default|description|
|:---|:---|:---:|:---||
|starN|number|yes| |重新渲染选中的星星数|

### .initEvent()

初始化事件

##Event

|name|target|param|condition|
|:---|:---|:---:|:---:|
|touchend|组件本身||在点击组件时触发调用|
