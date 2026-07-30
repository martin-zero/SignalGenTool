## SignalGenTool
### 概述
自用脚本，Go语言萌新。由于工作中QNX中间件->Unity HMI链路中车控信号信号需要跨语言维护，通过该脚本将同事宏定义格式信号表自动转为C#形式信号表，顺便借此机会学习go语言。

### 安装方法
[Releases](https://github.com/martin-zero/SignalGenTool/releases)

### 自行编译
sgtool工具使用Go语言编写，因此语言电脑有Go语言环境才可进行编译，推荐使用1.26.5版本或更高版本进行编译。

#### go语言环境:
- [官网下载](https://go.dev/dl/) 
- 使用包管理器下载

#### 构建方法:
``` shell
# 在项目目录下
go build
```

#### 安装(可选):
``` shell
go install
```
使用该命令会将目标添加到 `$GOPATH/bin` 目录下，请保证 `$GOPATH/bin` 已经在系统环境变量中

### 使用方法

```
Usage of sgtool:
  -i 路径
        要解析的头文件的文件路径路径
  -o 路径
        目标文件的生成路径路径 (default "./") 
```

例如:
``` shell
# 将当前目录的信号表头文件 'signal.h' 解析为C#代码，生成到 '~/UnityProject/Assets/Scripts/'目录下
# 之后在该目录下即可看到生成物VehicleSignalTable.cs
sgtool -i signal.h -o ~/UnityProject/Assets/Scripts/
```
