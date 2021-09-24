# CocoaPods Packager

[![Build Status](http://img.shields.io/travis/CocoaPods/cocoapods-packager/master.svg?style=flat)](https://travis-ci.org/CocoaPods/cocoapods-packager)
[![Coverage Status](https://img.shields.io/coveralls/CocoaPods/cocoapods-packager.svg)](https://coveralls.io/r/CocoaPods/cocoapods-packager?branch=master)
[![Gem Version](http://img.shields.io/gem/v/cocoapods-packager.svg?style=flat)](http://badge.fury.io/rb/cocoapods-packager)
[![Code Climate](http://img.shields.io/codeclimate/github/CocoaPods/cocoapods-packager.svg?style=flat)](https://codeclimate.com/github/CocoaPods/cocoapods-packager)

CocoaPods plugin which allows you to generate a framework or static library from a podspec.

This plugin is for CocoaPods *developers*, who need to distribute their Pods not only via CocoaPods, but also as frameworks or static libraries for people who do not use Pods.

## Why should I use Pods if I'm targeting developers who don't use Pods?

There are still a number of advantages to developing against a `podspec`, even if your public distribution is closed-source:

1. You can easily use the Pod in-house in an open-source style. This makes step-by-step debugging and multi-project development a breeze.
2. You can pull in third-party dependencies using CocoaPods. (CocoaPods Packager is even capable of mangling symbols to improve compatibility with any symbols that might appear in the integrating app.)
3. You can declaratively specify build settings (e.g. frameworks, compiler flags) in your `podspec`. This is easier to maintain and replicate than build settings embedded in your Xcode project.

## Installation

```sh
$ gem install cocoapods-packager
```

or add a line to your Gemfile:

```ruby
gem "cocoapods-packager"
```

then run `bundle install`.

This installs Packager as a CocoaPods plugin.

## Usage

```bash
$ pod package KFData.podspec
```

See also `pod --help`.

## 手动编译

> [参考资料](https://www.jianshu.com/p/a253017eecce)

下载完成源码之后， 找到目录下cocoapods-packager/lib/cocoapods_packager.rb 文件， 打开可以看到其版本是 1.5.0。 可以修改成1.6.0。避免之后被gem源覆盖。

安装Gem依赖包
进入工程目录（即 cocoapods-packager.gemspec 文件所在目录）执行命令安装相关依赖项

bundler install
如果没有安装 bundler，则先使安装 bundler

gem install bundler
构建gem包
gem依赖包安装完成后，执行构建命令

sudo gem build cocoapods-packager.gemspec
执行成功后会生成 cocoapods-packager-1.6.0.gem 文件

本地安装gem包
将前面生成的 cocoapods-packager-1.6.0.gem 文件执行本地安装

sudo gem install cocoapods-packager-1.6.0.gem -l 
安装过程中会将 cocoapods-packager-1.6.0.gem 和其相关依赖 gem 安装到默认目录

检查安装结果
安装完成执行

gem list 

或者：
gem list | grep cocoapods-packager

可以看到gem已安装列表里多了 cocoapods-packager (1.6.0）这个版本，这个版本就有 --local 参数

作者：刘明洋
链接：https://www.jianshu.com/p/a253017eecce
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
