<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [jetbrains-url-schemes](#jetbrains-url-schemes)
  - [Requirement](#requirement)
  - [JB各IDE-toolTag说明](#jb%E5%90%84ide-tooltag%E8%AF%B4%E6%98%8E)
  - [checkout某个仓库，使用对应对应IDE打开](#checkout%E6%9F%90%E4%B8%AA%E4%BB%93%E5%BA%93%E4%BD%BF%E7%94%A8%E5%AF%B9%E5%BA%94%E5%AF%B9%E5%BA%94ide%E6%89%93%E5%BC%80)
  - [打开某仓库，某文件及移动到对应行列位置](#%E6%89%93%E5%BC%80%E6%9F%90%E4%BB%93%E5%BA%93%E6%9F%90%E6%96%87%E4%BB%B6%E5%8F%8A%E7%A7%BB%E5%8A%A8%E5%88%B0%E5%AF%B9%E5%BA%94%E8%A1%8C%E5%88%97%E4%BD%8D%E7%BD%AE)
  - [相关文档](#%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# jetbrains-url-schemes
链接跳转到JB IDE且自动执行某个动作

## Requirement
- 安装JetBrains Toolbox
- 安装需要打开的JB家IDE，比如WebStorm

## JB各IDE-toolTag说明

scheme链接中使用tag

```js
{
  idea: {
    name: 'IntelliJ IDEA',
    tag: 'idea',
  },
  appcode: {
    name: 'AppCode',
    tag: 'appcode',
  },
  clion: {
    name: 'CLion',
    tag: 'clion',
  },
  pycharm: {
    name: 'PyCharm',
    tag: 'pycharm'
  },
  phpstorm: {
    name: 'PhpStorm',
    tag: 'php-storm'
  },
  rubymine: {
    name: 'RubyMine',
    tag: 'rubymine'
  },
  webstorm: {
    name: 'WebStorm',
    tag: 'web-storm'
  },
  rider: {
    name: 'Rider',
    tag: 'rd'
  },
  goland: {
    name: 'GoLand',
    tag: 'goland'
  }
}
```

## checkout某个仓库，使用对应对应IDE打开

cloneUrl支持HTTPS/SSH

```
jetbrains://${toolTag}/checkout/git?checkout.repo=${cloneUrl}&idea.required.plugins.id=Git4Idea
```

例子
```
jetbrains://web-storm/checkout/git?checkout.repo=git@github.com:alanhg/alfred-workflows.git&idea.required.plugins.id=Git4Idea
```


## 打开某仓库，某文件及移动到对应行列位置

```
jetbrains://${toolTag}/navigate/reference?project=${project}&path=${filePath}:${lineIndex}:${columnIndex}
```

例子
```
jetbrains://web-storm/navigate/reference?project=alfred-workflows&path=README-zh.md:25:10
```


## 相关文档
- https://github.com/JetBrains/toolbox-browser-extension
