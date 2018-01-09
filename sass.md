## vue 项目 使用sass
1.安装
> `npm install node-sass --save-dev
npm install sass-loader --save-dev`

2.配置webpack.base.config.js
`{
    test: /\.vue$/,
    loader: 'vue-loader',
    options: {
      loaders: {
        'scss': 'style-loader!css-loader!sass-loader'
      }
    }
  }`
