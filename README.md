# LXGW Bright Code 网络字体仓库

[![NPM Version](https://img.shields.io/npm/v/%40joshuasu%2Flxgwbright-code-web?labelColor=cb0000&color=ffffff)](https://www.npmjs.com/package/@joshuasu/lxgwbright-code-web)

## 简介
[LXGW Bright Code](https://github.com/lxgw/LxgwBright-Code) 是由 [Monaspace Argon](https://github.com/githubnext/monaspace) 与 [霞鹜文楷系列字体](https://github.com/lxgw/LxgwWenKai) 合并而成的字体一款开源中文字体。字体详情请参阅原字体仓库。

> ### 感谢
> 
> 本仓库改进自[LXGW WenKai / 霞鹜文楷 网络字体仓库](https://github.com/CMBill/lxgw-wenkai-web)，以适配LXGW Bright Code，感谢原作者的辛勤付出。
> 
> 具体的改进如下：
> - 适配 LXGW Bright Code 字体
> - 打包成npm包，方便集成到本地项目中
> - 优化GitHub Action

为使原字体更适合进行网络分发，本仓库使用 Github Action，利用[中文网字计划](https://chinese-font.netlify.app/)开发的[字体分包工具](https://github.com/KonghaYao/cn-font-split)对原字体分包，网页加载时只需获取所使用的文字所在的分包，大幅降低所需加载的大小，提升网页加载速度。并已提交 [npm 包](https://www.npmjs.com/package/@callmebill/lxgw-wenkai-web)，进一步利用公开 CDN。


本仓库的版本号与字体原仓库版本号保持一致。提供从本仓库建立时的最新版本 `v2.611` 及之后的版本。

可以点击[效果展示](https://sujoshua.github.io/LxgwBright-Code-web/)，查看字体样式。

## 使用

### NPM

首先安装本包

``` bash
# npm
npm install @joshuasu/lxgwbright-code-web
# yarn
yarn add @joshuasu/lxgwbright-code-web
# pnpm
pnpm add @joshuasu/lxgwbright-code-web
```

然后在项目中引入
``` js
import "@joshuasu/lxgwbright-code-web";
```


这样引入的 `style.css` 可以调用仓库包含的所有字体，使用字体时以表格中所示的 `font-family`，`font-style` 与 `font-weight`  在 CSS 中调用即可。


| 字体                               |  `font-family`                | `font-style` | `font-weight` |
| --------------------------------  | ----------------------------- | ------------- | -----------  |
| LxgwBright Code                   | `LxgwBright Code`             | `normal`      |  `400`       |
| LxgwBright Code Italic            | `LxgwBright Code`             | `italic`      |  `400`       |
| LxgwBright Code Light             | `LXgwBright Code Light`       | `normal`      |  `300`       |
| LxgwBright Code Light Italic      | `LxgwBright Code Light`       | `italic`      |  `300`       |
| LxgwBright Code ExtraLight        | `LXgwBright Code ExtraLight`  | `normal`      |  `200`       |
| LxgwBright Code ExtraLight Italic | `LXgwBright Code ExtraLight`  | `italic`      |  `200`       |

* font-style 为 normal 可以不填，默认即为 normal

如果只需某一特定的字体，也可只引用其对应分包的 CSS 文件，这样可以减少引入不必要的文件，减小最终的产物文件。
```js
# 引入 LxgwBright Code
import "@joshuasu/lxgwbright-code-web/400.css";
# 引入 LxgwBright Code Italic
import "@joshuasu/lxgwbright-code-web/400-italic.css";
# 引入 LxgwBright Code Light
import "@joshuasu/lxgwbright-code-web/300.css";
# 引入 LxgwBright Code Light Italic
import "@joshuasu/lxgwbright-code-web/300-italic.css";
# 引入 LxgwBright Code ExtraLight
import "@joshuasu/lxgwbright-code-web/200.css";
# 引入 LxgwBright Code ExtraLight Italic
import "@joshuasu/lxgwbright-code-web/200-italic.css";
```

## CDN

直接将文后提供的[链接](#链接)以 `<link>` 的形式添加到网页的 `<head>` 内即可

```html
<html>
<head>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@joshuasu/lxgwbright-code-web@latest/style.css" />
  <style>
    body {
      font-family: "LxgwBright Code";
      font-weight: normal;
    }
  </style>
</head>
<body>
  
</body>
</html>
```
然后在 CSS 中同 Npm 中表格所示的 `font-family`，`font-style` 与 `font-weight` 进行调用即可。

同样如果只需某一特定的字体，可以只引入其对应分包的 CSS 文件。
| 字体                               | 链接                                                                               |
| --------------------------------- | ---------------------------------------------------------------------------------- |
| LxgwBright Code                   | `https://cdn.jsdelivr.net/npm/@joshuasu/lxgwbright-code-web@latest/400.css`        |
| LxgwBright Code Italic            | `https://cdn.jsdelivr.net/npm/@joshuasu/lxgwbright-code-web@latest/400-italic.css` |
| LxgwBright Code Light             | `https://cdn.jsdelivr.net/npm/@joshuasu/lxgwbright-code-web@latest/300.css`        |
| LxgwBright Code Light Italic      | `https://cdn.jsdelivr.net/npm/@joshuasu/lxgwbright-code-web@latest/3000-italic.css`|
| LxgwBright Code ExtraLight        | `https://cdn.jsdelivr.net/npm/@joshuasu/lxgwbright-code-web@latest/200.css`        |
| LxgwBright Code ExtraLight Italic | `https://cdn.jsdelivr.net/npm/@joshuasu/lxgwbright-code-web@latest/200-italic.css` |



## 链接
### 自行部署
如果下方提供的链接连接效果不甚理想，建议自行部署并配合自己的 CDN 使用，可以直接克隆本仓库到服务端、对象存储等。

### 使用 CDN
目前已作为 npm 包上传到 npmjs，可以使用 npm 包的镜像链接引用。

#### 使用 JsDelivr 对 npm 包的 CDN（推荐）

```
https://cdn.jsdelivr.net/npm/@joshuasu/lxgwbright-code-web@latest/style.css
```

也可指定版本号，将链接中的 `$VERSION` 替换为目标版本号（但 npm 的语义化版本号会省略版本号数字开头的 0，具体版本号建议先查询 [npmjs](https://www.npmjs.com/package/@joshuasu/lxgwbright-code-web?activeTab=versions)）如 `2.611` 或 `v2.611` 均可。只提供 `v2.611` 之后的版本，即本仓库建立时上游的最新版本。

```
https://cdn.jsdelivr.net/npm/@joshuasu/lxgwbright-code-web@$VERSION/style.css
```