# 流转状态显示框

##Example
使用
```html
  <ul 
    widget="ystatus" 
    all-status="已受理;维修中;已完成;已评价" 
    status="已完成"
   />
```

##Option

|name|type|required|default|description|
|:---|:---|:---:|:---||
|allStatus|string|yes||所有要显示的流转状态，字符串形式且以";"隔开|
|status|string|yes||流转状态已完成步骤显示|

##Methods

###.renderStatus()

根据allStatus数据渲染出所有流转状态并根据status数据显示到已完成的步骤
