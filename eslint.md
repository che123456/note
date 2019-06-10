vue cli3.0 引入eslint 结合vscode使用
它的目标是提供一个插件化的javascript代码检测工具。官网地址

最近一个项目里，最开始使用 cli3.0 搭建的时候没有默认选用 eslint ，导致现在有的人使用其他编辑器，就会出现格式错乱的情况。所以引入 eslint 做代码检测

第一步 （安装）

npm install eslint eslint-config-airbnb-base eslint-plugin-import eslint-plugin-vue --save-dev 引入关于 eslint 的一些依赖 当你的 package.json 里出现

"eslint": "^5.16.0",
"eslint-config-airbnb-base": "^13.1.0",
"eslint-plugin-import": "^2.17.3",
"eslint-plugin-vue": "^5.2.2",
说明安装成功

第二步（检测）

在 package.json 文件的命令行 sctipts 里面添加

"lint": "eslint --ext .js,.vue src" 批量检测代码

vue cli3.0 引入eslint 结合vscode使用

Example：

vue cli3.0 引入eslint 结合vscode使用

运行

npm run lint

vue cli3.0 引入eslint 结合vscode使用

面板会提示有xx个错误，而且会标明哪个文件。

而且会提示你是用 --fix 进行修复

第三部（修复）

上面的 "lint": "eslint --ext .js,.vue src" 修改为 eslint --ext .js,.vue src --fix

运行

npm run lint

vue cli3.0 引入eslint 结合vscode使用

这是就没有 errors 和 warning了

至此 eslint 已经引入,并且可以自动修复。但是 --fix 并不能完全修复代码，比如

vue cli3.0 引入eslint 结合vscode使用

就会提示 'vm'被定义但是未被使用

vue cli3.0 引入eslint 结合vscode使用

就需要手动删掉

配合 vscode 使用

目的： 使用vscode到达保存就自动fix的效果 。

1.安装

下载地址

2.安装 eslint

vue cli3.0 引入eslint 结合vscode使用

3.设置 eslint

打开 文件-》首选项-》设置，找到并打开 setting.json 添加如下配置

{
 "eslint.enable": true, // 是否开启检测
 "editor.tabSize": 2,
 "eslint.autoFixOnSave": true,
 "files.associations": {
 "*.vue": "vue"
 },
 "eslint.options": {
 "extensions": [
  ".js",
  ".vue"
 ]
 },
 "eslint.validate": [
 "javascript",{
  "language": "vue",
  "autoFix": true
 },
 "html",
 "vue"
 ],
}
4.安装 Vetur 插件

Vetur 能够在 vscode1 编辑器里面识别 .vue 文件并且对文件可以：

语法高亮
语法提示,补全功能
语法检测
5.配置完成

这个时候就会有提示

vue cli3.0 引入eslint 结合vscode使用

按 ctrl+s 就自动修复了

vue cli3.0 引入eslint 结合vscode使用

tips： 有时按一次 ctrl+s 修复不了，多按几次就好了，不过我一般写一段就 ctrl+s 一下，问题不大。

