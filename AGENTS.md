# AGENTS.md

## 语言要求（重要）

- 本项目所有沟通、注释、文档、提交说明一律使用**中文**。
- 编写任何新文件（说明、笔记、配置注释等）也要用中文，不要在仓库里留下英文文档或英文说明。
- 用户明确要求在 `AGENTS.md` 中强调：用中文。

## 项目是什么

- 纯静态网页（HTML + CSS + JS），**没有** `package.json`、构建脚本、测试框架或 dev server。
- 目标是借鉴 `ReferenceExample\html5up-ethereal` 模板（HTML5 UP 的 "Ethereal"）来搭建自己的网页。
- 当前仓库里的 `index.html`、`images`、`assets` 都是从 `ReferenceExample\html5up-ethereal` 复制过来的。

## 结构与入口

- 页面入口是根目录的 `index.html`（单页、横向滚动的 side-scrolling 模板）。
- 真正被加载的样式是 `assets/css/main.css`，脚本是 `assets/js/main.js`（依赖 `jquery.min.js`）。
- `ReferenceExample\html5up-ethereal` 是原始模板，需要对照/复制内容时以它为参照；它的 `README.txt` 详细说明了 panel / span / color 等修饰类用法。

## 关键约定与易错点

- **改样式要改 `assets/css/main.css`，不是 `assets/sass/*.scss`。** 仓库里没有配置 Sass 编译（无 node_modules、无 npm 脚本），`assets/sass` 只是源码参考，改了 `.scss` 不会生效，必须同步改 `main.css`（或自行安装并运行 sass 编译）。
- 横向滚动页面要求元素有固定宽度：整段的 `panel` 用 size 修饰（`small`/`medium`/`large`），或内部元素用 `span-*` 修饰来满足宽度。不要随意删掉这些修饰类，否则布局会错。
- 滚动行为（拖拽、滚轮转横向、键盘左右键、边缘滚动区）在 `assets/js/main.js` 顶部的 `settings` 里可开关/调参。
- 图片资源放在 `images/`，画廊用 `images/gallery/fulls`（大图）和 `images/gallery/thumbs`（缩略图）。

## 预览方式

- 没有专用命令。直接用浏览器打开 `index.html`，或起一个任意静态文件服务器（如 `python -m http.server`）访问即可。

## 其他

- `.gitignore` 已忽略 `node_modules`、`dist`、构建/测试产物，以及 `note-haruki*` 下的 Obsidian 配置（`/.obsidian`、`**/.$*`）。`note-haruki*` 是个人笔记目录，不要把它当作项目源码来改。
- `.npmrc` 设了 `save-exact=true`：若以后引入 npm 依赖，安装会锁定精确版本。
