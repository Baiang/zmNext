# yog2 node v8升级方案

老项目node v8升级方案。注：目前支持win10、centos7环境，其它环境未测试。

### package.json升级或需要安装模块
```
{
    "node-forge": "^0.7.5",
    "node-gyp": "^3.7.0",
    "yog2": "^1.6.0",
    "yog2-kernel": "^1.9.2",
    "xml2json": "^0.9.0",
}
```

### 升级方式
1. 更新package.json
2. npm install -g node-gyp
3. npm install(windows在git Bash图形界面下执行)
4. npm rebuild （npm install有node-gyp错误时执行，依然有错误，查看下方问题1，再执行npm rebuild；如果bcrypt编译报错，查看问题2）

### 开发遇错反馈：
在本地进行开发报错后，及时进行反馈，当前升级方案会持续维护。
https://github.com/Baiang/zmNext/issues

### windows环境问题
问题1：node-gyp报错， 确认是否windows平台缺少编译环境

解决：以管理员身份运行 npm install –production windows-build-tools -g

问题2：bcrypt编译报错

解决：运行 npm install bcrypt --msvs_version=2012

问题3：npm rebuild卡着不动、npm install卡着

解决：重新运行 npm install 或 yarn，或者翻墙。

### macOS环境问题
问题1：node-gyp报错
解决：在终端运行xcode-select --install
