# iOSDebugTips
####Q: 在用xib或storyboard搭建UI时，一个UI元素一开始用UILabel显示，后来发现需要添加点击事件，这时不要偷懒在label上覆盖一个button，当出现Bug后很难发现真正的显示控件是label。
####A: 应该把label替换成Button或者直接给label添加点击手势
![enter image description here](https://github.com/aimchina/iOSDebugTips/blob/master/Image/QQ20160128-0%402x.png)

####Q: 从一个显示tabBar的viewController push到一个新的页面，我们往往会隐藏tabBar，如果从这个页面再pop回去的时候，iOS7下tabBar可能会消失。
####A: pop时使用动画可以解决
```objective-c
[self.navigationController popToRootViewControllerAnimated:YES];
```

####Q: 当显示不定长的UI元素时，像时间、价格或者数量，这类数字元素往往不能换行显示，位数过大时很容易会出现“...”显示不全。
####A: 同一行内不要显示过多的数字元素，一般不超过2个，位置相邻的元素要做拼串，然后用同一个label显示，如下图淘宝的设计。如果必须要在一行内显示多于一个的UI元素，可以把label的区域大小重叠设置，这样即使位数过多，也可以完全显示，只是数字重叠，不会出现“...”的情况
![enter image description here](https://github.com/aimchina/iOSDebugTips/blob/master/Image/971A62E7-86DD-42ED-8A83-46F2D549ABB4.png)
