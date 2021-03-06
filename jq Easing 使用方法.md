`jquery easing`是jq一款可以自定义动画的函数，animate( properties [, duration] [, easing] [, complete] )有四个参数

使用需要引入jquery,jquery.easing.js

### 32种easing效果

linear
swing
easeInQuad
easeOutQuad
easeInOutQuad
easeInCubic
easeOutCubic
easeInOutCubic
easeInQuart
easeOutQuart
easeInOutQuart
easeInQuint
easeOutQuint
easeInOutQuint
easeInExpo
easeOutExpo
easeInOutExpo
easeInSine
easeOutSine
easeInOutSine
easeInCirc
easeOutCirc
easeInOutCirc
easeInElastic
easeOutElastic
easeInOutElastic
easeInBack
easeOutBack
easeInOutBack
easeInBounce
easeOutBounce
easeInOutBounce

```javascript
(function ($) {
				
	jQuery.extend( jQuery.easing,               //选择easing参数，可选的值有32种
	{  
	    easeOutExpo: function (x, t, b, c, d) {  //easeOutExpo
		return (t==d) ? b+c : c * (-Math.pow(2, -10 * t/d) + 1) + b;  
	    },  
	    easeOutBounce: function (x, t, b, c, d) {  //easeOutBounce
		if ((t/=d) < (1/2.75)) {  
		    return c*(7.5625*t*t) + b;  
		} else if (t < (2/2.75)) {  
		    return c*(7.5625*(t-=(1.5/2.75))*t + .75) + b;  
		} else if (t < (2.5/2.75)) {  
		    return c*(7.5625*(t-=(2.25/2.75))*t + .9375) + b;  
		} else {  
		    return c*(7.5625*(t-=(2.625/2.75))*t + .984375) + b;  
		}  
	    },  
	}); 
        $(function () {                          //执行 滑行到top500px的地方
            $(myElement).animate({  
		    top: 500,  
		    opacity: 1  
		}, 1000, 'easeOutBounce');  
        });
			
})(jQuery);

```
使用jQuery内置动画函数如slideUp()、slideDown()等来指定easing效果，以下两种方法都可以：

```javascript
$(myElement).slideUp(1000, method, callback});  
$(myElement).slideUp({  
    duration: 1000,   
    easing: method,   
    complete: callback  
});
```
