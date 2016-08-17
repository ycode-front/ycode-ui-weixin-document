# 超时记录组件

ytimeout这个组件用来计时，有两个按钮，一个计时按钮(必须)，一个刷新按钮；在点击刷新及页面刷新后不用重新开始，而是记录上次计时的位置，继续计时

## Example

使用

```javascript
        $(window).ytimeout({
            // 计时器的唯一id
            id:'demoit',
            // 计时时长，以毫秒为单位
            duration: 10*1000,
            // 计时的步长 默认为一秒钟
            step: 50,
            // 初始化的时候调用
            onstart:function(){
                console.log('start it');
            },
            // 进行中的时候调用，每一秒调用一次
            onprogress: function(progress){
                console.log('进度:' + progress);
                $('.js-progress').css('width', progress*100+'%');
            },
            // 在恢复的时候调用
            onresume:function(){
                console.log('resume it');
            },
            // 计时结束的时候调用
            onfinish: function(){
                console.log('finish it');
            }
        })
        $('.js-start').on('touchend', function(){
            $(window).ytimeout().start();    
        });
        
        $('.js-refresh').on('touchend', function(){
            location.href = location.href;
        });
当做一个jquery对象的方法来使用，直接调用ytimeout方法
```
## options
|name|type|required|default|description|
|:---|:---|:---|:---|:---|
|id|string|no|''|每个计时器的标识符，唯一ID|
|duration|number|no|0|计时的时长，以毫秒为单位|
|step|number|no|1000|计时的步长，以毫秒为单位|
|onstart|function|no|空函数|计时开始时触发的函数|
|onprogress|function|no|空函数|每隔一个步长的时间调用一次，指定样式的代码描述了进度条的样式|
|onresume|function|no|空函数|点击刷新的时候调用的函数|
|onfinish|function|no|空函数|计时结束的时候调用的函数|

## Method

## Event
