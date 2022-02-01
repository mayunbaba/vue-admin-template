# admin-template

## 代码格式规范

- eslint  
- prettier  
- vscode 配置自动格式化  

## git提交规范

- 约定式提交规范
- commitizen: git提交规范化工具 全局安装(https://www.jianshu.com/p/36d970a2b4da)  
- commitlint: 用于检查提交信息 (https://blog.csdn.net/qq_38290251/article/details/111646491)
- pre-commit： git hooks 钩子
- lint-staged 可以让你当前的代码检查**只检查本次修改更新的代码，并在出现错误的时候，自动修复并且推送** 
- husky: 是 `git hooks` 工具  
```
yarn add husky -D
npx husky install // 生成husky文件
npm set-script prepare "husky install" // 设置prepare脚本
yarn prepare
// 添加commitlint 的 hook到husky中，并指令在commit-msg的hooks下执行npx --no-install commitlint --edit "$1" 指令 husky中生成commit-msg文件
npx husky add .husky/commit-msg 'npx --no-install commitlint --edit "$1"'
npx husky add .husky/pre-commit 'npx lint-staged'
```
npm 需要在 7.X 以上版本

## tag的使用
```
git pull --tag 拉取远端tag
git tag -n  查看tag
git tag -a "1.0.0" -m "提交信息"
git tag -d tag-name  删除本地tag
git push origin :refs/tags/tag-name 删除远端tag
git push --tag
```

## Project setup

```
yarn install
```

### Compiles and hot-reloads for development

```
yarn serve
```

### Compiles and minifies for production

```
yarn build
```

### Lints and fixes files

```
yarn lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
