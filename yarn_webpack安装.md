
#问题
    ['yarn' 不是内部或外部命令，也不是可运行的程序]

#解决 
##命令:npm install -g yarn

#问题
    cmd命令中输入 yarn 仍然不存在命令;
    首先看系统变量Path中有没有yarn的路径，如果没有添加上。例如我的是F:\Yarn\bin;
如果用户变量中有默认的PATH，将其删掉。
需找到window系统环境变量;添加例如下面yarn下的bin目录;
    D:\Program Files\nodejs\node_global\node_modules\yarn\bin
    再运行
##命令:yarn命令;
成功如下:
        D:\webpack_demo>yarn
        yarn install v1.16.0
        info No lockfile found.
        [1/4] Resolving packages...
        [2/4] Fetching packages...
        [3/4] Linking dependencies...
        [4/4] Building fresh packages...
        
        success Saved lockfile.
        Done in 0.07s.
#在项目路径下打开cmd 输入 
##命令: yarn init -y 初始化;
cmd窗口出现:
    D:\webpack_demo>yarn init -y
    yarn init v1.16.0
    warning The yes flag has been set. This will automatically answer yes to all    questions, which may have security implications.
    success Saved package.json
    Done in 0.06s.

项目目录出现 yarn.lock 文件;

#安装webpack 和webpack-cli;
##命令: yarn add webpack webpack-cli -D
    成功如下:
    D:\webpack_demo>yarn add webpack webpack-cli -D
    yarn add v1.16.0
    [1/4] Resolving packages...
    [2/4] Fetching packages...
    info fsevents@1.2.9: The platform "win32" is incompatible with this module.
    info "fsevents@1.2.9" is an optional dependency and failed compatibility    check. Excluding it from installation.
    [3/4] Linking dependencies...
    [4/4] Building fresh packages...
#webpack打包
#命令:npx webpack
##会将当前目录下的index.js入口文件;打包在当前目录下新生成的dist 文件夹中 的main.js;
webpack默认配置 入口文件就是index.js 生成的就是main.js;需要更改则需要自行配置webpack.config.js;
成功如下:
    D:\webpack_demo>npx webpack
    Hash: bd2fcabc3824a17365ba
    Version: webpack 4.35.0
    Time: 276ms
    Built at: 2019-06-20 23:38:10
      Asset       Size  Chunks             Chunk Names
    main.js  949 bytes       0  [emitted]  main
    Entrypoint main = main.js
    [0] ./src/index.js 19 bytes {0} [built]
    
    WARNING in configuration
    The 'mode' option has not been set, webpack will fallback to 'production' for   this value. Set 'mode' option to 'development' or 'production' to enable  defaults for each environment.
    You can also set it to 'none' to disable any default behavior. Learn more:  https://webpack.js.org/configuration/mode/
#测试;
新建一个index.html;在html中引入利用webpack打包生成的dist中main.js文件;
自行运行测试;
#手动配置webpack.config.js
         // node语法以下配置
     let path = require('path');
     
     module.exports = {
         mode:'development',//模式 一种是production生产模式  development开发模式(    压缩与未压缩的区别)
         entry:'./src/index.js',//入口
         output:{
             filename:'bunde.js',//打包后的文件名
             path:path.resolve(__dirname,'build'),//路劲必须是绝对路径;在当前生成的文件   夹目录名;存放打包后的文件
         }
     
     }

