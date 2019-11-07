# kgo
k`s golang helper/library/utils  
golang 函数库/工具集,仅测试支持64位linux

### 文档
[![GoDoc](https://godoc.org/github.com/kakuilan/kgo?status.svg)](https://godoc.org/github.com/kakuilan/kgo)
[![Go Report Card](https://goreportcard.com/badge/github.com/kakuilan/kgo)](https://goreportcard.com/report/github.com/kakuilan/kgo)
[![Build Status](https://travis-ci.org/kakuilan/kgo.svg?branch=master)](https://travis-ci.org/kakuilan/kgo)
[![codecov](https://codecov.io/gh/kakuilan/kgo/branch/master/graph/badge.svg)](https://codecov.io/gh/kakuilan/kgo)
[![Code Size](https://img.shields.io/github/languages/code-size/kakuilan/kgo.svg?style=flat-square)](https://github.com/kakuilan/kgo)
[![Starts](https://img.shields.io/github/stars/kakuilan/kgo.svg)](https://github.com/kakuilan/kgo)
[![Downloads](https://img.shields.io/github/downloads/kakuilan/kgo/total.svg)](https://github.com/kakuilan/kgo/releases)

### 函数接收器说明
- *KFile* 为文件操作
- *KStr* 为字符串操作
- *KNum* 为数值操作
- *KArr* 为数组(切片/字典)操作
- *KTime* 为时间操作
- *KConv* 为类型转换操作
- *KOS* 为系统和网络操作
- *KEncr* 为加密操作
- *KDbug* 为调试操作

### 测试
```shell
#清理包
go mod tidy

#单元测试
go test

#压测
time go test -bench=. -run=none
time go test -v -bench=. -cpu=4 -benchtime="10s" -timeout="15s" -benchmem

#代码覆盖率
go test -cover #概览

go test -coverprofile=coverage.out #生成统计信息
go test -v -covermode=count -coverprofile=coverage.out
go tool cover -func=coverage.out #查看统计信息
go tool cover -html=coverage.out #将统计信息转换为html

#性能分析
time go test -bench=. -benchmem -memprofile memprofile.out -cpuprofile profile.out
go tool pprof profile.out
go tool pprof -http=192.168.56.10:8081 /usr/bin/dot profile.out
```

