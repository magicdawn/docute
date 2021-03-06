# 自定义

Cusotmizing Docute is as fun as playing with Lego bricks.

## 导航栏

```js
new Docute({
  title: 'Docute',
  nav: [
    {
      title: 'Home',
      link: '/'
    },
    {
      title: 'GitHub',
      link: 'https://github.com/leptosia/docute'
    }
  ]
})
```

`title` 选项的默认值是 `<title>` 标签的内容，因此这个选项不是必需的。

显示效果请参考本站的导航栏。

## 侧边栏

侧边栏一般用于跨页面的导航， 不过正如本站的导航栏，它也显示了一个版本选择器和语言选择器。

```js
new Docute({
  sidebar: [
    {
      title: 'Guide', // 可选的
      links: [
        {
          title: 'Getting Started',
          link: '/guide/getting-started'
        },
        {
          title: 'Installation',
          link: '/guide/installation'
        },
      ]
    }
  ]
})
```

查看 [sidebar](../options.md#sidebar) 选项的文档来了解更多细节。

## 多版本文档

假设你的 Git 项目有一个 `master` 分支用于存放最新文档，以及 `v0.1` `v0.2` 分支用于旧版本的文档，你可以用一个 Docute 文档网站来显示多个版本的文档，通过使用 [`overrides`](../options.md#overrides) 和 [`sourcePath`](../options.md#sourcepath) 选项就能办到。

```js
  // 让这些路径从不同的地方获取 Markdown 文件
  overrides: {
    '/v0.1/': {
      sourcePath: 'https://raw.githubusercontent.com/user/repo/v0.1'
    },
    '/v0.2/': {
      sourcePath: 'https://raw.githubusercontent.com/user/repo/v0.2'
    }
  },
  // 用 `versions` 选项在侧边栏添加一个版本选择器
  versions: {
    'v1 (Latest)': {
      link: '/'
    },
    'v0.2': {
      link: '/v0.2/'
    },
    'v0.1': {
      link: '/v0.1/'
    }
  }
```

## 自定义字体

Apply custom fonts to your website is pretty easy, you can simply add a `<style>` tag in your HTML file to use [Google Fonts](https://fonts.google.com/):

```html
<style>
/* Import desired font from Google fonts */
@import url('https://fonts.googleapis.com/css?family=Lato');

/* Apply the font to body (to override the default one) */
body {
  font-family: Lato, sans-serif;
}
</style>
```

<button v-on:click="insertCustomFontsCSS">Click me</button> to toggle the custom fonts on this website.

By default a fresh Docute website will use system default fonts.

## 覆盖 CSS

默认 [CSS 变量](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables)：

```css
:root {
  --accent-color: rgb(6, 125, 247);
  --sidebar-width: 280px;
  --sidebar-bg: white;
  --sidebar-section-title-color: rgb(136, 136, 136);
  --border-color: #eaeaea;
  --header-height: 60px;
  --code-font: SFMono-Regular,Consolas,Liberation Mono,Menlo,Courier,monospace;

  --tip-color: rgb(6, 125, 247);
  --success-color: #42b983;
  --warning-color: #ff9800;
  --danger-color: rgb(255, 0, 31);
}
```
