## fixSidebar
+ A jquery plugin fix the sidebar automatically when the content area is too long
+ 演示地址 http://www.jx3pve.com/macro

####使用方法
```javascript
fixSidebar(selector,top,bottom,triggerScroll)
fixSidebar('sidebar',30,80,100)
```

####参数说明
+ selector是选择器，会被传入到jQuery中，如果没有则退出函数，故如果懒人的话直接加载在全局JS文件中即可。
+ top为传入的距顶位置，这个的作用是，如果存在fix的panel导航或用户条时，不传值的话则为0。
+ bottom为传入的距底位置，这个作用是距底位置，如果你还有全局的底部导航等时，应该设置此值，可以稍微比底栏高度再大一点点保留间距感，不传值的话则为0。
+ triggerScroll则是在v0.3的时候新加的，当时由于自己私人项目中的这个页面还有头部横幅，于是如果必要的话，你还可以设置，触发fix时的值，比如这个页面则在250以后开始触发。
内置自动判定了默认在页面中的实际水平坐标。当侧边栏长度小于页面长度时默认依据顶部来计算位置，当侧边栏长度大于页面时才依旧底部来计算位置。

####补充说明
+ 在最近副本栏目的应用中，由于幻灯滚动的存在，我发现会出现一点滚动异常，思忖良久，发觉是受幻灯overflow的BFC管理而导致的，最终的解决方法是给传入的selector设置overflow:hidden，必须由它自己管理约束自己。此项已自动在v0.4中加入在函数中了，无需再额外css设置。
+ 当你的侧边栏中如果有js载入的内容，并且他们在此插件加载之后才会加载，你需要给其对应元素设置一个min-height以免计算错误（v0.4）
 
