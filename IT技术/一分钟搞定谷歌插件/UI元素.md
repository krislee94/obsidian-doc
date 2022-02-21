[相关API](https://developer.chrome.com/docs/extensions/mv3/user_interface/#tooltip)


# 注册浏览器


通过`action` 字段注册

```json
{
  "name": "My Awesome action MV3 Extension",
  ...
  "action": {
    ...
  }
  ...
}

```

# 添加徽章

徽章在浏览器图标的顶部显示带有最多四个字符的彩色横幅。它们只能由`"action"`在清单中声明的​​扩展使用。

使用徽章来指示扩展程序的状态。[Drink Water Event](https://developer.chrome.com/docs/extensions/mv3/samples#search:drink)示例显示一个带有“ON”的标记，以向用户显示他们成功设置了警报，并且在分机空闲时不显示任何内容。

```js
chrome.action.setBadgeText({text: 'ON'});
chrome.action.setBadgeBackgroundColor({color: '#4688F1'});

```


# 指定工具栏图标

特定于工具栏的图标注册在清单`"default_icon"`下方的字段中。[`action`](https://developer.chrome.com/docs/extensions/reference/action/)鼓励包括多种尺寸以适应 16-dip 空间。建议至少使用 16x16 和 32x32 尺寸。

```json

{
  "name": "My Awesome page_action Extension",
  ...
  "action": {
    "default_icon": {
      "16": "extension_toolbar_icon16.png",
      "32": "extension_toolbar_icon32.png"
    }
  }
  ...
}

```


# 命令


扩展可以定义特定的[命令](https://developer.chrome.com/docs/extensions/reference/commands/)并将它们绑定到一个组合键。`"commands"`在该字段下的清单中注册一个或多个命令。


```json
{
  "name": "Tab Flipper",
  ...
  "commands": {
    "flip-tabs-forward": {
      "suggested_key": {
        "default": "Ctrl+Shift+Right",
        "mac": "Command+Shift+Right"
      },
      "description": "Flip tabs forward"
    },
    "flip-tabs-backwards": {
      "suggested_key": {
        "default": "Ctrl+Shift+Left",
        "mac": "Command+Shift+Left"
      },
      "description": "Flip tabs backwards"
    }
  }
  ...
}

```

