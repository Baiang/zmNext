# v8升级方案

本地开发掌门老项目node v8升级方案。注：未进行反复测试，谨慎在生产环境进行部署

### 升级方式
1. 更新package.json
2. npm install -g node-gyp
3. npm install(windows在git Bash图形界面下执行)
4. npm rebuild （npm install有node-gyp错误时执行，依然有错误，查看问题1，再执行npm rebuild；如果bcrypt编译报错，查看问题2）

### 开发遇错反馈：
大家在本地进行开发报错后，及时进行反馈，我这边会及时进行修复和解决。
https://github.com/Baiang/zmNext

### windows环境
问题1：node-gyp报错， 确认是否windows平台缺少编译环境
解决：运行 npm install –production windows-build-tools -g

问题2：bcrypt编译报错
解决：运行 npm install bcrypt --msvs_version=2012

问题3：npm rebuild卡着不动、npm install卡着
解决：重新运行 npm install 或 yarn，或者翻墙。

### macOS环境
问题1：node-gyp报错
解决：在终端运行xcode-select --install
