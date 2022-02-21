---
author： 李大洲
title：制作一个json2ts插件。把json文件转为interface
---
![[Kris Blog.png]]

[项目地址](https://github.com/krislee94/json2ts-choreme)


## 背景

写node项目的时候，总想着偷懒，一些返回的参数，总是不愿意建interface 去给变量来赋类型。

这种情况较为突出的表现在 es查询的地方....

打个比方：

es搜索引擎订单的字段就超过100个。如果一个个手写.d.ts文件那么就太浪费时间了。这个时候就一个工具来帮助我们实现。

```js
interface ISomRquestParam {
	name:string;
	age:number;
	isNumber: boolean;
}

```



 ## 了解谷歌插件

要上手一个谷歌插件，其实非常简单。
可以说是一个分钟就可以搞定一个插件。
[[谷歌插件API]]  来查看具体的一些信息


一个谷歌插件包含了 [[背景脚本]]、 [[内容脚本]]、[[选项页面]]、[[UI元素]] 和各种逻辑文件。主要使用的技术就是基本的HTML、CSS、 JavaScript。


[[插件入门]] 



## 项目搭建

1.  使用vite来搭建。[vite中文官网](https://vitejs.cn/)

```
# yarn
yarn create vite json2ts-chrome --template vue-ts

# npm 6.x
npm init vite@latest json2ts-chrome --template vue-ts

# npm 7+, 需要额外的双横线：
npm init vite@latest json2ts-chrome -- --template vue-ts

# pnpm
pnpm create vite json2ts-chrome -- --template vue-ts

```


2. 导入UI

这里我们使用的是对vue3支持比较好的 [vant](https://vant-contrib.gitee.io/vant/#/zh-CN) 来支撑。

在vite.config.ts里。 导入vant的样式

```ts
import { defineConfig } from "vite";
import vue from "@vitejs/plugin-vue";
import styleImport from "vite-plugin-style-import";


// https://vitejs.dev/config/
export default defineConfig({
  plugins: [
    vue(),
    styleImport({
      libs: [
        {
          libraryName: "vant",
          esModule: true,
          resolveStyle: (name) => {
            return `vant/es/${name}/style`;
          },
        },
      ],
    }),
  ],
});



```



3. `public`文件

public 文件会被直接打包到根目录下，因此在`public`文件下建立 manifest.json 。 加入images文件。

同时我们需要使用哪些`vant`的组件，就要在 入口`ts`文件里导入...

```ts
import { createApp } from "vue";
import App from "./App.vue";
//全局注册组件 vant 更多组件注册参考（https://vant-contrib.gitee.io/vant/v3/#/zh-CN/advanced-usage#zu-jian-zhu-ce）
import { Search, Field, Form, CellGroup, Button, Popup, Dialog } from "vant";

createApp(App)
  .use(Search)
  .use(Field)
  .use(Form)
  .use(CellGroup)
  .use(Button)
  .use(Popup)
  .use(Dialog)
  .mount("#app");

```

4. `manifest.json` 文件注册 icon，注册默认的弹窗 html

```json
{
    "manifest_version": 2,
    "name":"json2ts",
    "version":"1.0",
    "description":"a simple json to ts interface",
    "icons": {
        "16":"images/JSON16.png",
        "48":"images/JSON48.png",
        "128":"images/JSON200.png"
    },
    "browser_action":{
       "default_icon":{
        "48":"images/JSON48.png",
        "64":"images/JSON64.png"
       },
       "default_title":"json2ts",
       "default_popup":"index.html"
    }

}

```

5.  UI样式

UI这里不过多讨论，主要讨论一下。我们使用`monaco`  

[monaco-editor](https://github.com/microsoft/monaco-editor)


![[Pasted image 20220215193430.png]]

这是风格类似vscode编辑器。


使用：

```ts
import * as monaco from "monaco-editor";



//初始化
 onMounted(() => {
      //@ts-ignore
      editor = monaco.editor.create(document.getElementById("cpyf"), {
        language: "typescript",
        theme: "vs-dark",
        readOnly: false,
        minimap: { enabled: true },
        autoDetectHighContrast: true,
      });
    });

//塞入值

editor.setValue(result);

```



