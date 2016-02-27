# gulp-pack

gulp-pack是为前端开发人员准备的一个自动化工具，实质上是对gulp常用插件的封装。

它只需要在全局安装一次，可以最大程度的减少node_modules对开发目录的污染，并节省您的时间。

目前包含以下功能，以后还会继续增加:

* 简易的服务器（webserver）
* 页面自动刷新（livereload）
* 自动补全CSS前缀（autoprefixer）
* CSS预处理（stylus，默认不开启）

###第一步：安装（全局）

```
npm install -g gulp-pack
```


###第二步：启动

在命令行中定位到Web文件所在的目录，然后执行如下代码：

```
pack
```


###配置（可选）

通过在package.json中加入pack属性，可以自定义以下选项：

* http          ---- 简易Web服务器的端口，关闭该项功能请设置false
* livereload    ---- 自动刷新页面，关闭该项功能请设置false
* autoprefixer  ---- 自动补全css属性前缀，关闭该项功能请设置false
* open          ---- 是否在启动服务后自动打开浏览器，默认关闭
* watch         ---- 要监控的各文件类型的路径，关闭该项功能请设置false
* stylus        ---- 是否监听.styl类型的文件，默认关闭

如果目录中还没有package.json文件，可在命令行中输入`npm init`，然后一直按回车即可自动生成。

###示例：

```
{
  "name": "my-project",
  "version": "1.0.0",
  "description": "",
  "author": "",


  "pack": {
    "root": "./client/",
    "http": 3001,
    "livereload": {
      "port": 4001,
      "enable": true
    },
    "autoprefixer": ["> 0%"],
    "open": false,
    "watch": {
      "js": [
        "./client/**/*.js"
      ],
      "css": [
        "./client/**/*.css"
      ],
      "stylus": [
        "./client/**/*.styl"
      ],
      "html": [
        "./client/**/*.html"
      ]
    }
  }


}
```
