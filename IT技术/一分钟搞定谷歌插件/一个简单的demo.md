一个简单的demo只需要这几个文件。

![[Pasted image 20220211140924.png]]


### manifest.json


这是主要文件。

```json 
{

"manifest_version": 2,

"name": "stock helper",

"version": "1.0",

"description": "a simple info of stock",

"icons": {

"16": "images/icon16.png",

"48": "images/icon48.png",

"128": "images/icon128.png"

},

"browser_action": {

"default_icon": {

"19": "images/icon19.png",

"38": "images/icon38.png"

},

"default_title": "stock helper",

"default_popup": "popup.html"

},

"permissions": [

"http://hq.sinajs.cn/list=*"

]

}


```

`default_popup": "popup.html`  这个popup.html 是入口html 文件。

`default_icon` 是浏览器icon

`main.js`主要就是 js文件，实现界面操作方式等

`permissions` 是需要获取权限



就这样几个文件就能构成一个简单的demo



