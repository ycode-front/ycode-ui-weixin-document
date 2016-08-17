# 图片上传组件

yupload这个组件是在上传图片完成，数据发送至服务器后；此时对图片进行编辑，增删操作。

## Example

使用

```html
<input
    type="hidden"
    value="1231"
    url="/uploadfile"
    widget="yupload"
    preview="http://shp.qpic.cn7sbqjOBJomcuvVJ6iacVrbMJaoJZkFUIq4nzQZUIqzTKziam7ibg/"
/>
```
## Options
|name|type|required|default|description|
|:---|:---|:---|:---|:---|
|value|string|no||服务器返回的上传图片时的id标识|
|url|string|no||进行添加上传图片时服务器端对应的路径|
|preview|url|no||服务器返回的上传的图片对应的url地址|
|max-amount|number|no|4|上传图片的最大数量|

## Method

## Event
