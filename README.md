# 微信小程序学习 起手式DEMO仿肯德基
## 小程序是啥？
微信小程序本质上来说就是一个 HTML 5（移动网页） 应用，用view、scoll-view代替了div标签等，换汤不换药。在微信中运行时，微信小程序获得更多的系统权限。首先是数据缓存能力，这可以让用户在打开一个小程序的时候将程序的主要框架缓存到微信上，下一次就可以快速打开了。微信创始人张小龙曾说过，微信应用号希望实现的目标是“用完即走，无需安装和卸载”，也就是说以后当你要使用一个应用时，只需要在微信里搜索就可以直接使用了，如摩拜、美团等小型使用低频的app使用该套技术可大量节省开发成本。
## 起手做什么？
由于本人吃货一枚，家门口有一家KFC，之前KFC的app经常有一些福利卷，既然用惯了这个便捷实惠的app，于是就做它了。
言归正传，先来分析一下一步一步该做啥。
### 完成的功能：附近位置选择-联动菜单导航-模拟数据-抽屉式购物车-获取用户微信信息-收集前面所有数据模拟生成订单 
### 用到的工具和文档：
1. **开发调试工具:**   [微信小程序平台教程](https://mp.weixin.qq.com/debug/wxadoc/dev/),安装好最基本的啦！稍微过一遍简易文档。
2. **开发‘字典’文档:**  [微信小程序开发教程手册文档](https://www.w3cschool.cn/weixinapp/9wou1q8j.html)功能使用方法都在上面挺全的。
3. **easy-mock:**  [easy-mock](www.easy-mock.com)模拟后端数据，后面会简单介绍配置。
4. **腾讯地图API:**   [腾讯地图小程序](http://lbs.qq.com/qqmap_wx_jssdk/index.html)有地点搜索、关键词输入提示、逆地址解析(坐标位置描述)地址解析(地址转坐标)距离计算、获取城市列表、获取城市区县的一步配置教程。
5. **WeUI**  [WeUI github](https://github.com/weui/weui-wxss)微信专用的结构样式组件库，加速开发速度，BEM规范代码，增强可读性

## 目录结构
    ├── app.js
    ├── app.json
    ├── app.wxss
    ├── pages
    │   ├── .DS_Store
    │   ├── KFC
    │   │   ├── KFC.js
    │   │   ├── KFC.wxml
    │   │   └── KFC.wxss
    │   ├── card
    │   │   ├── card.js
    │   │   ├── card.wxml
    │   │   └── card.wxss
    │   ├── halladdress
    │   │   ├── .DS_Store
    │   │   ├── halladdress.js
    │   │   ├── halladdress.wxml
    │   │   └── halladdress.wxss
    │   ├── index
    │   │   ├── index.js
    │   │   ├── index.wxml
    │   │   └── index.wxss
    │   ├── logs
    │   │   ├── logs.js
    │   │   ├── logs.json
    │   │   ├── logs.wxml
    │   │   └── logs.wxss
    │   ├── menu
    │   │   ├── index.html
    │   │   ├── menu.js
    │   │   ├── menu.wxml
    │   │   └── menu.wxss
    │   ├── order
    │   │   ├── order.js
    │   │   ├── order.wxml
    │   │   └── order.wxss
    │   └── takeout
    │       ├── message
    │       │   ├── message.js
    │       │   ├── message.wxml
    │       │   └── message.wxss
    │       ├── qqmap-wx-jssdk.min.js
    │       ├── takeout.js
    │       ├── takeout.wxml
    │       └── takeout.wxss
    ├── style
    │   ├── .DS_Store
    │   └── weui.wxss
    └── utils
        └── util.js

#### 页面注册
#### app.json
        "pages": [
        "pages/index/index",   // 首页
        "pages/KFC/KFC",       // K金商城页
        "pages/menu/menu",     // 菜单页
        "pages/card/card",     // 卡包页
        "pages/order/order",   // 订单页
        "pages/takeout/takeout",  // 外卖地图页
        "pages/takeout/message/message", // 填写外卖信息页
        "pages/halladdress/halladdress", // 附近餐厅页
        "pages/logs/logs" // 日志页
        ]
我们可以通过官网的文档或W3C教程上初始化了一个小程序目录，小程序的每个页面都放在pages目录下
每次添加一个新页面，都需要先在app.json.page下注册。


