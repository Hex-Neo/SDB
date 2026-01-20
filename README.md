# 工具介绍

SDB代码静态分析工具，全称 SecureDefectBenchmark 安全缺陷基准测试工具

本工具是一款支持Java的代码静态分析工具，功能优势：

当前版本基于功能强大的CodeQL静态分析引擎能力进行二次开发

经过优化的 Java CWE 审计规则

SAST功能支持离线使用，不需要联网，不外传数据，安全可靠

SAST分析，不会对代码进行完整编译，支持分析不完整的项目代码

整合了开源组件扫描功能，此功能需联网使用，配置请求头请参考上手指南

命令行+web页面两种运行方式，支持像ez那样，输入sdb web即可进入web页面，端口号：6190


注：

win平台运行sdb.exe

需要自行下载codeql v2.23.8 添加至环境变量，规则已内置

其他平台使用jar文件即可

cloudflare验证真人绕过请参考 "sdb上手指南.pdf" 中的  Init初始化 

如果配置了请求头，初始化网络连接还是失败，建议换个网，去kfc吧，后续会提供常用组件全版本本地数据库，就不需要联网使用依赖漏洞扫描功能了

# 功能介绍

<img width="690" height="456" alt="image" src="https://github.com/user-attachments/assets/059fd5d3-d364-49cc-ba8e-b9c1991320fb" />



web页面（依然主推命令行用法）

<img width="1737" height="840" alt="image" src="https://github.com/user-attachments/assets/53389fa0-6bd9-4676-9ff4-f96fba3baf7f" />
<img width="2559" height="1365" alt="image" src="https://github.com/user-attachments/assets/a7165a3f-cc7f-414e-8217-c7810297d357" />

# 手动编译代码环境依赖

依赖环境	推荐版本	下载地址

Java	8u471	https://www.oracle.com/java/technologies/downloads/archive/#JavaSE

CodeQL	2.23.8	https://github.com/github/codeql-cli-binaries

# 后续开发计划

支持更多编程语言

基于 AST+neo4j 进行污点分析
