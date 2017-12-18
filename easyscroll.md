## 基于vue的滚动条组件
> [项目线上例子](https://garveyzuo.github.io/easyscroll.github.io/#/)
> [项目源代码](https://github.com/GarveyZuo/EasyScroll)
###  安装依赖
```
 npm isntall --save easyscroll
```
### 安装vue-jsx
```
 npm install babel-plugin-syntax-jsx babel-plugin-transform-vue-jsx babel-helper-vue-jsx-merge-props babel-preset-es2015 --save-dev
 ```
### 修改项目根目录下.babelrc文件
```
{
  "presets": ["es2015"],
  "plugins": ["transform-vue-jsx"]
}
```
### 导入项目main.js
```
import EasyScroll from 'easyscroll'
Vue.use(EasyScroll)
```

### 基本用法

> 安装完easyscroll之后，在组件中直接引用EasyScrollbar组件就行，产生滚动条的内容作为EasyScroll的$slot插入到滚动条组件中，注意插入到滚动条组件中内容 需要一个外层的包裹，即上面代码中的#wrapper div，其内部才是真正动态的内容。

```
 <template>
  <div  style="width:90%;">
    <EasyScrollbar :barOption="colorSizeOption">
      <div  id="wrapper" style="width:100%;height: 300px;">
        <div style="height: 500px;background-color: greenyellow;text-align: center;">
          最简单的应用
        </div>
      </div>
    </EasyScrollbar>
  <div>
</template>

<script>
export default {
 data() {
    return {
      colorSizeOption:{
        barColor:"#959595",   //滚动条颜色
        barWidth:6,           //滚动条宽度
        railColor:"#eee",     //导轨颜色
        barMarginRight:0,     //垂直滚动条距离整个容器右侧距离单位（px）
        barMaginBottom:0,     //水平滚动条距离底部距离单位（px)
        barOpacityMin:0.3,      //滚动条非激活状态下的透明度
        zIndex:"auto",        //滚动条z-Index
        autohidemode:true,     //自动隐藏模式
        horizrailenabled:true,//是否显示水平滚动条
      }
    };
  }
};
</script>

```

### 配置参数

参数名|说明
---|---
barColor|滚动条颜色
barWidth|滚动条宽度
railColor|导轨颜色
barMarginRight|垂直滚动条距离整个容器右侧距离单位（px）
barMaginBottom|水平滚动条距离底部距离单位（px
barOpacityMin|滚动条非激活状态下的透明度
zIndex|滚动条z-Index
autohidemode|自动隐藏模式
horizrailenabled|是否显示水平滚动条
### 示例
```
barOption:{
  barColor:"#959595",   //滚动条颜色
  barWidth:6,           //滚动条宽度
  railColor:"#eee",     //导轨颜色
  barMarginRight:0,     //垂直滚动条距离整个容器右侧距离单位（px）
  barMaginBottom:0,     //水平滚动条距离底部距离单位（px)
  barOpacityMin:0.3,      //滚动条非激活状态下的透明度
  zIndex:"auto",        //滚动条z-Index
  autohidemode:true,     //自动隐藏模式
  horizrailenabled:true,//是否显示水平滚动条
}
```
