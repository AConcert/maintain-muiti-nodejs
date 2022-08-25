---
title: windows 下管理多个版本的 Node.js
tags: windows, 多版本 node,npm
---


1. 在控制面板中卸载已安装的 node.js。卸载完成后，[官网](https://github.com/coreybutler/nvm-windows)推荐去`C:\Users\<user>\AppData\Roaming`文件夹下删除`npm`整个文件夹，为安装 node.js 提供一个干净的环境。（记好自己之前 node 安装过的依赖，方便后面重装）

   

2. [官网](https://github.com/coreybutler/nvm-windows)下载最新版`nvm`, 安装在默认位置，我的是在 `C:\Users\<user>\AppData\Roaming\nvm`

   

3. 切换为 `taobao 的安装源`

   ```
   nvm node_mirror https://npm.taobao.org/mirrors/node/
   nvm npm_mirror https://npm.taobao.org/mirrors/npm/
   ```

   切换完后，去`C:\Users\<user>\AppData\Roaming\nvm\settings.txt`里面确认一下。

   

4. 安装需要的 node.js 版本

   例如，安装 v10.13 版本的 node.js，可以通过以下命令完成：

   ```
   nvm install v10.13.0
   ```

   使用 v10.13 版本的 node.js，命令如下：

   ```
   nvm use v10.13.0
   ```

   查看当前安装的 node.js 版本列表

   ```
   nvm ls
   ```

   查看当前使用的 node.js 的版本

   ```
   node -v
   ```

   查看随 node.js 默认安装的 npm 的版本

   ```
   npm -v
   ```

   如果到这里没有报错，那么后面的文字就不用看了。最后再贴一下 **angular/cli** 各个版本兼容的 **node.js** 及 **typescript** 版本：[angular-cli-node-js-typescript-compatiblity-matrix.csv](https://gist.github.com/LayZeeDK/c822cc812f75bb07b7c55d07ba2719b3#file-angular-cli-node-js-typescript-compatiblity-matrix-csv)

   

5. npm 安装显示 complete，但运行 `npm -v` 报错

   ```
   Cannot find module C:\Program Files\nodejs\node_modules\npm\bin\npm-cli.js
   ```

   [node.js](https://nodejs.org/en/download/releases/) 官网中找到对应版本的 npm 版本号，在 [npm镜像官网](https://npm.taobao.org/mirrors/npm/) 中找到并下载，解压后将文件夹复制到 `C:\Users\<user>\AppData\Roaming\v10.13\node_modules` 目录下，并重命名为**npm**，再次运行 `npm -v` 查看是否成功。

   

 **angular/cli** 各个版本兼容的 **node.js** 及 **typescript** 版本：[angular-cli-node-js-typescript-compatiblity-matrix.csv](https://gist.github.com/LayZeeDK/c822cc812f75bb07b7c55d07ba2719b3#file-angular-cli-node-js-typescript-compatiblity-matrix-csv)

 

