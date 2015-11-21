# nvm

这几天实验室配了新电脑，就装了 Ubuntu 14.04 玩。实在用腻了 Windows 。

之前的Node使用源代码编译的 `5.0` ，看了 alsotang 的这篇文章，装了 nvm ，需要在 `~/.profile` 文件里加入导出 nvm 环境变量的代码才能使用。

装了 nvm 之后，之前自己编译 `5.0` 会在 `nvm ls` 中出现一个 system 。

nvm 将 node 装在了 `~/.nvm/versions/node/vx.x.x` 。

不同版本的 node ， npm 的版本也不同。如 `0.12` 对应的 npm 版本是 `2.11` , `5.0` 对应的是 `3.3` 。

nvm 通过环境变量劫持了 node 的路径，如果在 `~/.profile` 文件中删除导出 nvm 环境变量的语句， 则默认使用 system ，在 `/usr/local/bin/node` 。

每次修改 `~/.profile` 文件需要重启 shell 才能生效。

# How to use it

### 安装
```
$ nvm install 5.0
```
安装完成之后会自动切换到安装的版本。

### 切换

```
$ nvm use 5.0
$ nvm use system
```

### 已安装列表
```
$ nvm ls
->    v5.0.0
      system
node -> stable (-> v5.0.0) (default)
stable -> 5.0 (->v5.0.0) (default)
isjs -> iojs (-> N/A) (default)
```

### 可用列表
```
$ nvm ls-remote
```

### 安装路径
```
$ nvm which 5.0
/home/x-web/.nvm/versions/node/v5.0.0/bin/node
$ which node
/home/x-web/.nvm/versions/node/v5.0.0/bin/node
```

### 运行
```
$ nvm run [version] app.js
$ nvm exec [version] [node] app.js
```

### 设置默认版本
```
$ nvm alias default 5.0
```
每次启动 shell 使用的 node 版本。

### 恢复环境变量
```
$ nvm deactivate
```
好像没什么用。 nvm 还是可以使用。

[read more](https://github.com/creationix/nvm)
or
`$ nvm help`
