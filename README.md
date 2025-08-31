# JiYuTrainerNext - 便捷的极域电子教室助手

> ⚠️ **注意：本项目为非官方修改版本！**  
> 原项目开源地址：[imengyu/JiYuTrainer](https://github.com/imengyu/JiYuTrainer)

---

<p align="center">
  <a href="#">
    <img alt="JiYu Trainer" src="JiYuTrainerLogo256.png" width="128">
  </a>
</p>

<p align="center">
  <img alt="JiYu Trainer Title" src="JiYuTrainerTitle.png">
</p>

<p align="center"><b>打破极域电子教室的控制，还你操作自由</b></p>

<p align="center">
  <a href="#"><img src="https://img.shields.io/badge/language-C++-blue.svg" alt="语言"></a>
  <a href="https://github.com/illusoryday/JiYuTrainerNext/releases"><img src="https://img.shields.io/badge/version-1.7-green.svg" alt="版本"></a>
  <a href="https://github.com/illusoryday/JiYuTrainerNext/blob/master/LICENSE"><img src="https://img.shields.io/badge/license-MIT-orange.svg" alt="许可证"></a>
</p>

---

## 📖 简介

本软件专为对抗极域电子教室的严格控制而设计。如果您的学校机房使用极域电子教室监控学生电脑，这款软件可能会帮到您。

> 是否遇到过这些困扰？
> - 老师讲课节奏缓慢，想自己操作却被全屏广播限制？
> - 拔掉网线获得自由后，却无法观看老师的演示？
> - 被强制黑屏，无法进行任何操作？

**JiYuTrainerNext** 可以解决这些问题！它能在不被发现的情况下，将极域的全屏广播自动转换为窗口模式，让您既能自由操作电脑，又能观看老师演示，实现学习与自由两不误。

如果您喜欢这个软件，请给项目一个⭐星星支持！您的认可是我持续更新的最大动力！

## ⚡ 功能特性

- **📺 广播窗口化**：将全屏广播转为窗口模式，不影响观看演示
- **🔧 进程管理**：内置强杀、启停极域 StudentMain.exe 进程功能
- **🔓 密码破解**：支持新版极域解锁和卸载密码破解
- **👁️ 反监视**：有效防止教师端监视您的电脑
- **🛡️ 防控制**：阻止教师通过极域控制您的电脑
- **⌨️ 命令监控**：自由选择是否允许教师端远程执行的命令
- **💬 消息发送**：向同学电脑发送消息或执行命令

## 📦 下载安装

[下载最新版本](https://raw.githubusercontent.com/illusoryday/JiYuTrainerNext/master/Release/JiYuTrainer.exe)

> **提示**：由于软件需要对极域电子教室进行必要操作（远程注入、模块替换），部分杀毒软件可能会误报。请添加至白名单或暂时关闭杀毒软件。

---

![软件截图](ScreenShots.png)

## 🎮 使用方法

本软件专为小白用户设计，默认情况下无需任何配置：

1. 下载 `JiYuTrainer.exe` 文件
2. 直接运行即可（软件已包含所有依赖库）
3. 最小化到系统托盘，软件会自动工作

![帮助文档](帮助.png)

## ❓ 常见问题

### Q: 教师端限制了U盘，如何复制软件到电脑？
**A:** 通过以下步骤卸载极域驱动后再插入U盘：

1. 以管理员身份运行CMD
   ![CMD](sc0.png)
2. 输入以下命令卸载TDFileFilter驱动：
   ```cmd
   sc stop TDFileFilter 
   sc delete TDFileFilter 
   ```
![sc](sc1.png)

### Q: 教师端限制了网络访问怎么办？
**A:** JiYuTrainer 可自动卸载网络驱动，若无效可尝试：

1. 使用PCHunter软件打开"驱动模块"页面
2. 找到并卸载"TDNetFilter.sys"驱动
3. 刷新网页即可正常访问
4. 建议同时结束极域相关进程，避免系统蓝屏

![pch](pchunter1.png)

## ✔️ 兼容性

**测试通过的极域版本：**

- 2010版 (5.01.64.942 / 5.01 Baseline)
- 2015豪华版
- 2016豪华版 (2.07.0.13488 / 2.07 CMPC)

**支持的操作系统：**

- Windows 7/8/8.1/10

**注意：由于近期较大更新，不再支持Windows XP。如需在XP系统使用，请下载旧版本。**

## 🔧 编译构建

**环境要求**

| 编译工具 | 推荐程度 |
|---------|---------|
| Visual Studio 2019+ | ⭐⭐⭐⭐⭐ (推荐) |
| GCC 4.7+ (需自行配置) | ⭐⭐ (不推荐) |

如需编译驱动模块，还需安装：

- WDK8 或更高版本

构建步骤：

1. 使用Visual Studio打开 JiYuTrainer.sln
2. 选择Release配置和x86平台
3. 右键生成JiYuTrainer项目
4. 在/Release目录获取生成的可执行文件

注：无需理会JiYuTrainerDriver的编译错误，源码中已包含预编译的驱动文件。

## 📚 使用的第三方库

- [Jiyu_udp_attack](https://github.com/ht0Ruial/Jiyu_udp_attack) - 由ht0Ruial大佬提供UDP攻击的原理代码
- [curl](https://github.com/curl/curl) - 用于自动更新模块
- [mhook](https://github.com/martona/mhook) - 用于 JiYu HOOKER 模块
- [MemoryModule](https://github.com/fancycode/MemoryModule)
- [XZip-XUnZip](https://github.com/yuanjia1011/XZip-XUnZip)

## 💬 其他说明

本项目由一名初中生修改维护，代码能力有限，如果您在使用过程中遇到问题，欢迎反馈！

如果您觉得这个项目有帮助，请给一个⭐星星并推荐给好友！

## 📄 许可证

[MIT License](LICENSE) - 自由、开源

---

**免责声明：本软件仅供教育目的使用，请遵守学校相关规定**
