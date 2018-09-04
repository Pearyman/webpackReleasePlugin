# webpack-Release-Plugin

### webpack.prod.conf.js
```

var WebpackReleasePlugin = require('webpackreleaseplugin')
var releaseConf = require('./release.conf')

...
...
...

const push = process.env.npm_config_push
if (push && releaseConf[push]) {
  console.log('推送地址：')
  console.log(releaseConf[push])
  console.log('')
  webpackConfig.plugins.push(new WebpackReleasePlugin({
    receiver: releaseConf[push],
    root: '/home/map/odp_cater/webroot/static/nscm'
  }))
}

```

### 使用方法

```
npm run build --push=liyanan    // 将dist目录下的打包文件通过插件推到远端
```


