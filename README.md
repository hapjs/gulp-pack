# Gulp-pack

Gulp-pack is a plugin which combines some common gulp plugins to make front-end development easier.

Gulp-pack can do these:

* simple webserver(webserver)
* auto-refresh page in browser(livereload)
* css auto prefix(autoprefixer)
* css pretreatment(stylus)

*More plugins will be combined in the futrue.*

## Install

Run terminal, and type code as below:

```
npm install -g gulp-pack
```

If your network is protected by the GFW, you may wanna try another command:

```
npm --registry https://registry.npm.taobao.org install -g gulp-pack
```

*Gulp-pack will be installed in global environment, which means, there won't be annoying node_modules folder in your project.*

## Run

Run terminal, go to your project path, and type code as below:

```
pack ./
```

Then you will see comments like these:

```
D:\Git\test>pack
[10:28:49] Webserver started at http://localhost:3001
监控js和html
监控css
工具已就绪，耗时507毫秒
```

It means gulp-pack is working.

## Optional Parameters

```
usage: gulp-pack [path] [options]
options:
  -p               Port to use [3001]
  -l --livereload  Livereload Port to use [4001]
  -h --help        Print this list and exit.
  -v --version     Print version.
```

## Extented package.json

You can add properties is package.json to enable/disable some functions.

| Property | Effect | Optional Config | Default | 
|:--------:|:------:|:---------------:|:-------:|
|http|web server port|true/false|true|
|livereload|auto refresh page in browser|true/false|true|
|autoprefixer|css auto prefix|true/false|true|
|open|open browser when server starts|true/false|false|
|stylus|monitor *.styl* files|true/false|true|
|watch|file path to be monitored|*see samples as below*||

If you don't modify package.json, gulp-pack works under default configs.

Here is a sample of package.json:

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