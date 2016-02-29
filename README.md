# gulp-pack

针对前端开发过程中最常用的需求，我们把一系列gulp插件封装成为一个简单的命令。

目前包含以下功能，以后还会继续增加:

* 简易的服务器（webserver）
* 页面自动刷新（livereload）
* 自动补全CSS前缀（autoprefixer，默认不开启）
* CSS预处理（stylus，默认不开启）

gulp-pack会被安装在全局目录，而不是你的项目目录下。

也就是说，你的项目中不会出现令人讨厌的node_modules文件夹。


###安装（全局）

```
npm install -g gulp-pack
```


###启动

在命令行中定位到你的项目目录，然后执行如下代码：

```
pack
```

或者要也可以指定路径

```
pack pages/
```

然后会看到如下内容：
```
D:\Git\test>pack
[10:28:49] Webserver started at http://localhost:3001
监控js和html
监控css
工具已就绪，耗时507毫秒
```

###命令行参数

```
usage: gulp-pack [path] [options]
options:
  -p               Port to use [3001]
  -l --livereload  Livereload Port to use [4001]
  -h --help        Print this list and exit.
  -v --version     Print version.
```

###package.json配置（可选）

默认情况下，你并不需要进行配置。

通过在package.json中加入pack属性，可以自定义以下选项：

* http          ---- 简易Web服务器的端口，关闭该项功能请设置false
* livereload    ---- 自动刷新页面，关闭该项功能请设置false
* autoprefixer  ---- 自动补全css属性前缀，关闭该项功能请设置false
* open          ---- 是否在启动服务后自动打开浏览器，默认关闭
* watch         ---- 要监控的各文件类型的路径，关闭该项功能请设置false
* stylus        ---- 是否监听.styl类型的文件，默认关闭

如果你的目录中还没有package.json文件，可在命令行中输入`npm init`，然后一直按回车即可自动生成。

###示例：

```
{
  "name": "my-project",
  "version": "1.0.0",
  "description": "",
  "author": "",


  "pack": {
    "root": "./",
    "http": 3001,
    "livereload": {
      "port": 4001,
      "enable": true
    },
    "autoprefixer": false,
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
