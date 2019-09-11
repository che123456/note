vue-devtools的安装与使用
一.在github上下载压缩包，github下载地址：https://github.com/vuejs/vue-devtools

二.解压到本地的某盘

三.用你的npm中进入该文件夹下

四.依次输:

1:npm install  （如果在这部报错的话，就改用cnpm install。  cnpm需要安装 安装地址）

2:npm run build         (这一步一定不要忘了，没有执行这一步的话，项目文件夹shells>chrome文件夹里会少一个src文件夹,如下图)

vue-devtools的安装与使用

五：修改shells>chrome文件夹下的mainifest.json 中的persistant为true

vue-devtools的安装与使用

六：我们找到谷歌浏览器的扩展程序功能，勾选开发者模式，然后我们将插件文件夹里的shells>chorme文件夹直接拖到页面中，完成安装。

（注意：如果我们没有执行第四部的npm run build，在这里会报错：无法加载背景脚本"build/background.js"）

七：在插件的目录下执行npm run dev，这个时候我们的插件就可以运行了,打开localhost:8080可以看到插件已经安装并运行了。

vue-devtools的安装与使用

八：我们在打开本地的其他项目时，就不需要在vue-devtools文件夹下执行npm run dev了，因为这个插件已经安装在浏览器中。接下来就愉快的调试你的vue项目吧。

 

更新：如果后期vue面板不出来，再到vue-devtools文件夹下执行一遍npm run dev。
