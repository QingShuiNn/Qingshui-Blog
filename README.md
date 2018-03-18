# 清水
A Vue.js 2.x + Express 2.0 + mongodb project

# 第一节:搭建项目
```bash
##1.创建Vue
#这里我们直接使用vue-cli
$ npm install --global vue-cli // 全局安装 vue-cli
$ vue init webpack my-project // 创建一个基于 webpack 模板的新项目
$ cd my-project
$ npm run dev
##2.创建Express
#通过应用生成器工具 express 可以快速创建一个应用的骨架
$ npm install express-generator -g
##3.重新设置端口及合并package.json
Vue及Express项目生成完成之后，我是这样做的：
1.将express目录移动至Vue-cli生成的项目下，重命名为server；
2.将sever的package.json中的dependencies全部复制粘贴至vue-cli的dependencies中
3.修改最外层目录下的package.json的script
"scripts": {
    "dev": "webpack-dev-server --config build/webpack.dev.conf.js",
    "client": "npm run dev",
    "server": "node ./server/bin/www",
    "lint": "eslint --ext .js,.vue src",
    "build": "node build/build.js"
  }
  注意：由于之后会创建Api，我们会给dev-server加入代理proxTable。并且为了便于修改，会将server的端口配置写在config/index.js中。
##4.启动项目
# 下载依赖
npm install
# 启动网页
npm run client
# 启动服务
npm run server

Ok
