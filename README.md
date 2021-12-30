# `standard-version-updater-pom`


[conventional-changelog/standard-version](https://github.com/conventional-changelog/standard-version)
版本管理工具 pom篇

## 安装

1. 在根目录创建 `package.json`.

```json
{
  "devDependencies": {
    "@soul-rat/standard-version-updater-pom": "^1.0.0"
  }
}
```

2. 安装npm包

```shell
$ npm install --save-dev @soul-rat/standard-version-updater-pom
```

## 配置


1. 根目录创建 `.versionrc.js`.

```js
// .versionrc.js
const xmlUpdater = require('@soul-rat/standard-version-updater-pom');
const xmlTracker1 = {
    filename: 'pom.xml',
    updater: xmlUpdater,
};
//如果是多模块，就添加多个xmlTracker
const xmlTracker2 = {
    filename: 'spring-web/pom.xml',
    updater: xmlUpdater,
};
const xmlTracker3 = {
    filename: 'spring-biz/pom.xml',
    updater: xmlUpdater,
};
const xmlTracker4 = {
    filename: 'spring-common/pom.xml',
    updater: xmlUpdater,
};
const xmlTracker5 = {
    filename: 'spring-dal/pom.xml',
    updater: xmlUpdater,
};
module.exports = {
    packageFiles: [xmlTracker1, xmlTracker2, xmlTracker3, xmlTracker4, xmlTracker5],
    bumpFiles: [xmlTracker1, xmlTracker2, xmlTracker3, xmlTracker4, xmlTracker5],
};
```
2. 执行对应的 standard-version 命令
