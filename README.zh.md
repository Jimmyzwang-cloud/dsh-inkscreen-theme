# dsh-inkscreen-theme

给 [DeepSeek Harness](https://github.com/deepseek-ai) 网页客户端（`dsh web`）用的墨水纸质感、苹果毛玻璃风主题。

给聊天界面套上柔和的毛玻璃面板、暖色米白/墨色配色和等宽字体的代码显示，并把侧栏的品牌区换成手写风格的 **"jimmy"** 字样，配一个小狗头像。

![主题预览](./assets/screenshot.png)

## 安装

```sh
dsh plugin add dsh-inkscreen-theme
```

或者把它加进你的 profile 的 `package.json`（`file:` 路径或 npm 依赖都行），并加到
`dsh.profile.bundles` 里，然后**重启** `dsh web`（这个插件涉及包身份和启动时注入的
CSS，热更新不够，需要完整重启才能生效）。

## 这个插件做了什么

- 注入一段 `<style>`，定义墨水纸/毛玻璃风格的 CSS 变量，作用于侧栏、对话框和滚动条。
- 监听侧栏的品牌区节点，把内容替换成手写风格字样（`Caveat` 网络字体，加载失败时
  退回系统自带的手写体），旁边配一个圆角小狗头像。

## 关于个性化

字样文字（"jimmy"）和头像图片都是写死在代码里的——这是个人定制主题，不是通用模板。
如果想换成自己的名字/头像，fork 之后改 `lib/client.js` 顶部的 `name` / `DOG_LOGO`
常量即可。

## 许可证

MIT，见 [LICENSE](./LICENSE)。
