# Soft Mesh Mapping - 软网格映射演示

## 项目简介

一个使用软网格映射技术实现图像变形效果的演示程序。通过鼠标拖拽可以实时交互式地变形图像，展示了网格映射算法和物理模拟的结合。

本项目基于 [EGE (Easy Graphics Engine)](https://github.com/x-ege/xege) 图形库开发，提供了一个简单而有趣的图形学演示案例。

## 功能特性

- ✨ 实时交互式的网格变形效果
- 🖱️ 鼠标拖拽实现直观的图像变形操作
- ⚙️ 可调节的网格弹性强度
- 🎨 支持多种图片格式（JPG、PNG、BMP、GIF）
- 🎯 基于物理模拟的平滑动画效果

## 依赖库

本项目依赖于 **EGE (Easy Graphics Engine)** 图形库：

- **项目地址**: https://github.com/x-ege/xege
- **官方网站**: http://xege.org
- **说明**: EGE 是一个简单易用的图形库，专为初学者设计，提供了便捷的图形绘制、图像处理、窗口管理等功能。它基于 Windows GDI+，可以在 Windows 平台上快速开发图形应用程序。

本仓库已包含 EGE 库的必要文件（头文件和静态库），位于 `ege/` 目录下，支持多种编译器和平台：
- MSVC (Visual Studio 2010/2015/2017/2019/2022)
- MinGW-w64
- 支持 x86 和 x64 架构

## 编译环境

### 支持的编译器

- **MSVC**: Visual Studio 2015 或更高版本（推荐使用 VS2019/VS2022）
- **MinGW-w64**: GCC 编译器（支持交叉编译）
- **C++ 标准**: C++14 或更高（VS2017+ 使用 C++17）

### 构建要求

- CMake 3.13 或更高版本
- Windows 平台（或使用交叉编译工具）

## 编译步骤

### 使用 CMake（推荐）

```bash
# 创建构建目录
mkdir build
cd build

# 配置项目
cmake ..

# 编译
cmake --build . --config Release
```

### 使用 Visual Studio

```bash
# 生成 Visual Studio 项目
mkdir build
cd build
cmake .. -G "Visual Studio 16 2019" -A x64

# 使用 Visual Studio 打开生成的 .sln 文件进行编译
```

### 交叉编译（Linux 环境编译 Windows 程序）

```bash
mkdir build
cd build
cmake ..
make
```

## 使用说明

### 启动程序

```bash
./soft-mesh-mapping [图片路径]
```

如果不指定图片路径，程序会提示选择一张图片文件。

### 操作方法

- **鼠标左键拖拽**: 拖动网格节点，实时变形图像
- **+ 键**: 增大网格弹性强度
- **- 键**: 减小网格弹性强度
- **ESC 键**: 退出程序

## 运行截图

![软网格映射效果 1](https://raw.githubusercontent.com/wysaid/soft_mesh_mapping/master/screenshot0.jpg)

![软网格映射效果 2](https://raw.githubusercontent.com/wysaid/soft_mesh_mapping/master/screenshot1.jpg)

## 技术说明

### 核心算法

- **网格映射**: 将图像划分为网格，每个网格单元由三角形组成
- **物理模拟**: 使用弹簧质点模型模拟网格的弹性变形
- **纹理映射**: 基于重心坐标的三角形纹理映射
- **实时渲染**: 60 FPS 的流畅交互体验

### 代码特性

- 兼容多种编译器（MSVC / MinGW / GCC）
- UTF-8 编码支持，避免乱码问题
- 双语支持：MSVC 编译显示中文，其他编译器显示英文
- 向后兼容：代码结构支持 VC6.0 等老版本编译器

## 项目结构

```
soft_mesh_mapping/
├── soft_mesh_mapping.cpp    # 主程序源代码
├── CMakeLists.txt            # CMake 构建配置
├── README.md                 # 项目说明文档
├── ege/                      # EGE 图形库
│   ├── include/              # 头文件
│   └── lib/                  # 静态库文件
├── screenshot0.jpg           # 效果截图 1
└── screenshot1.jpg           # 效果截图 2
```

## 作者信息

- **作者**: wysaid
- **博客**: http://wysaid.org
- **项目主页**: https://github.com/wysaid/soft_mesh_mapping

## 许可证

本项目仅供学习和参考使用。

## 相关链接

- [EGE 图形库官方仓库](https://github.com/x-ege/xege)
- [作者博客](http://blog.wysaid.org)
