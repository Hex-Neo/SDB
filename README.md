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
功能	                        命令	         完整命令样例
初始化（第一次使用必须初始化）	  init	          init
扫描分析Java项目源码	          scan	          scan -u 代码位置 -t Sast
扫描分析Java项目依赖	          scan	          scan -u 代码位置 -t dependency
全扫描                        	scan	          scan -u 代码位置 -t Auto
查询扫描分析历史记录	          hostory	        histort -l
导出扫描分析历史记录	          hostory	        histort -o 报告ID
拉取组件全版本漏洞信息	        pull	          pull -d com.alibaba.fastjsonpull
批量拉取组件全版本漏洞信息	    pull	          pull -t xxx.txt（此功能未经测试）
web页面操作	                  web	            web


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
