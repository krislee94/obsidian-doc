查看官方文档可以 查看 [谷歌英文文档api](https://developer.chrome.com/docs/extensions/mv3/getstarted/) 


一个谷歌插件包含了 [[背景脚本]]、 [[内容脚本]]、[[选项页面]]、[[UI元素]] 和各种逻辑文件。主要使用的技术就是基本的HTML、CSS、 JavaScript。

初步了解插件方式、一个简单的插件，如果不考虑交互，可能仅需要`manifest.json` `popup.html` 这两个文件。

我们可以看 [[一个简单的demo]]  。


## 入门


[[插件入门]]  这里介绍一个相对功能全面的功能


[官方插件demo](https://github.com/GoogleChrome/chrome-extensions-samples)  可以查看这里的代码参考


## API

Unless the doc says otherwise, methods in the `chrome.*` APIs are **asynchronous**:  

`chrome.*` 大部分都是异步的。


[API文档地址](https://developer.chrome.com/docs/extensions/reference/) 


**列几个常用的**  

* chrome.contentSettings   //内容设置
* chrome.cookies     // cookie设置
* chrome.declarativeNetRequest  //网络请求
* chrome.desktopCapture // 桌面捕获 可用于捕获屏幕、单个窗口或选项卡的内容。
* chrome.storage  // 缓存












