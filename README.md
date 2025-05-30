# flag-icons

> 一个精心策划的所有国家国旗的 SVG 收藏——加上 CSS 以便更容易集成。查看 [演示](https://flagicons.lipis.dev).

## 安装

你可以下载整个 [项目](https://github.com/lipis/flag-icons/archive/main.zip) 或者通过 npm 或 Yarn 安装：

```bash
npm install flag-icons
# or
yarn add flag-icons
```

## 使用方法

首先，您需要导入 CSS：

```js
import "/node_modules/flag-icons/css/flag-icons.min.css";
```

或者使用 SASS：

```html
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/gh/lipis/flag-icons@7.3.2/css/flag-icons.min.css"
/>
```

or use SASS:

```scss
@use "node_modules/flag-icons/sass/flag-icons";

// 或者使用自定义配置
@use "node_modules/flag-icons/sass/flag-icons" with (
  // 覆盖国旗目录路径
  $flag-icons-path: "node_modules/flag-icons/flags",

  // 仅包含特定国家的国旗
  $flag-icons-included-countries: ("gr", "de", "gb")
);
```

你可以在 [`sass/_variables.scss`] 中找到所有可用的变量(sass/_variables.scss).

要在文本中内联使用国旗，请在空的 `<span>` 元素中添加类 `.fi` 和 `.fi-xx` （其中 `xx` 是国家的 [ISO 3166-1-alpha-2 代码](https://www.iso.org/obp/ui/#search/code/)。如果您想要方形版本的国旗，请同时添加类 `fis`。示例：

```html
<span class="fi fi-gr"></span> <span class="fi fi-gr fis"></span>
```

您也可以将其应用于任何元素，但在这种情况下，您必须使用 `fib` 而不是 `fi`，然后就设置好了。这将使用以下 CSS 属性添加正确的背景：


```css
background-size: contain;
background-position: 50%;
background-repeat: no-repeat;
```
这意味着国旗只会出现在元素的中间，因此您必须手动设置正确的 4:3 比例尺寸，或者如果是方形的，还要添加 `flag-icon-squared` 类。

## 开发

克隆项目后运行 `yarn` 安装依赖项，然后您将能够：
构建 `*.scss` 文件

```bash
$ yarn build
```

在本地端口打开 `localhost:8000`

```bash
$ yarn start
```

要仅在CSS文件中包含特定国家的旗帜，请从[`_flag-icons-list.scss`](sass/_flag-icons-list.scss)文件中删除不需要的国家，然后重新构建。

## 致谢

- 没有 [koppi](https://github.com/koppi) 的精彩且已被删除的 SVG 旗帜集合，这个项目就不存在。
- 感谢 [Andrejs Abrickis](https://twitter.com/andrejsabrickis) 在 [npm](https://www.npmjs.com/package/flag-icons) 上提供了 `flag-icons` 这个名称。
