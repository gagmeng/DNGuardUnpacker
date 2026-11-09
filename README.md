# DNGuard 3.9.X ~ 4.9.7 静态全还原 脱壳工具

> 如侵权，请通过我的个人主页告知，我会进行删除

支持以下方式打包的程序：

1. 默认（Runtm外置）
2. 嵌入程序集
3. 单程序打包

支持 .NET Core/Framework/Standard。

此项目发布即 Archive，对于这方面的问题请不要来打扰我。

**此项目仅供学习交流**

> 研究用到的保护程序均从网上收集或加密网站加密得来，并没有使用官方工具。  
> 从未对官方工具进行逆向等违法操作，任何 clone 此仓库的人，禁止将其用于违法、黑灰产，请在学习后删除。

此项目基于 **CodeExplorer 的 DNGuard Static Unpacker** 二次开发。

---

## 使用说明

```text
# DNGuard 静态脱壳工具
用法：
  UniversalUnpacker inspect 输入文件 [--verbose]
  UniversalUnpacker probe 输入文件 [--deep] [--report 新建报告.json]
  UniversalUnpacker unpack 输入文件 新建输出文件 [选项]
  UniversalUnpacker source 输入文件 新建源码目录 [选项]
  UniversalUnpacker rename 已脱壳文件  （原地修复成员名并备份）
  UniversalUnpacker recover-types 已脱壳文件  （原地恢复类型并备份）

选项：
  --container 文件         提供原始 Single EXE 容器
  --source 目录            同时导出源码
  --recover-types          解包后恢复可证明的 object 类型
  --source-exporter 文件   指定源码导出器
  --rename-all             忽略反射名称保留（仍保留虚方法/序列化契约）
  --reference-dir 目录     源码导出额外依赖目录，可重复指定
  --allow-missing-references 缺依赖时仍导出源码，保留诊断，不保证可编译
  --async                  还原源码中的 async/await
  --prune-empty            清理源码中的无引用空方法
  --allow-execute          显式允许旧式 x86 动态提取
  --verbose                显示方法、节和数据头的详细诊断
  --deep                   probe 同时校验方法、算法候选及匿名字符串
  --quiet                  仅显示结果和错误
  --log-format legacy      保留旧版输出，供已有脚本使用
```

---

## Supported Packaging Methods

The following packaging methods are supported for the program:

1. Default (Runtm external)
2. Embedded Assembly
3. Single application packaging

Supports .NET Core/Framework/Standard.

This project is based on **CodeExplorer's DNGuard Static Unpacker**.

> **NOTE:** This is an incomplete prototype. You must modify the source code as needed to make it work for the version of DNGuard you are working on.

---

## USAGE

```text
UniversalUnpacker inspect <input_file> [--verbose]
UniversalUnpacker probe <input_file> [--deep] [--report <new_report.json>]
UniversalUnpacker unpack <input_file> <output_file> [options]
UniversalUnpacker source <input_file> <output_directory> [options]
UniversalUnpacker rename <unpacked_file>  (Fixes member names in-place and creates a backup)
UniversalUnpacker recover-types <unpacked_file>  (Restores types in-place and creates a backup)

Options:
  --container <file>         Provide the original Single EXE container
  --source <directory>       Export source code simultaneously
  --recover-types            Restore verifiable object types after unpacking
  --source-exporter <file>   Specify a source code exporter
  --rename-all               Ignore reflection-based name preservation (retains virtual methods/serialization contracts)
  --reference-dir <directory> Additional dependency directory for source export (can be specified multiple times)
  --allow-missing-references Export source code even if dependencies are missing (includes diagnostics; no guarantee of compilability)
  --async                    Restore async/await patterns in the source code
  --prune-empty              Remove unreferenced empty methods from the source code
  --allow-execute            Explicitly permit legacy x86 dynamic extraction
  --verbose                  Display detailed diagnostics for methods, sections, and data headers
  --deep                     Perform a deep probe (includes validation of methods, algorithm candidates, and anonymous strings)
  --quiet                    Display only results and errors
  --log-format legacy        Maintain legacy output format for compatibility with existing scripts
```
