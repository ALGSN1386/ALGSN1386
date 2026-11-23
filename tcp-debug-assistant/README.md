# TCP 调试助手

一个 Windows 桌面 TCP 网络调试工具。做串口/网口设备联调、服务端收发测试时，需要一个能快速连上、按 HEX 或文本收发、并能把往来报文记下来的小工具——这个程序就是干这件事的。

## 功能

- TCP 客户端连接：可填任意 IP 与端口（默认 `127.0.0.1:8899`）
- 三种收发模式：HEX / ASCII / UTF-8
- 实时统计 RX / TX 字节数
- 快捷命令栏（支持自定义，如 `AT\r\n`、`01 03 00 00 00 01`、`PING\r\n`）
- 收发日志自动落盘：`tcp_log_yyyyMMdd_HHmmss.txt`
- 快捷键 `Ctrl+Enter` 发送，可调主题配色

## 运行

1. 从本目录下载 `TCP-Debug-Assistant.exe`
2. 双击运行（Windows 系统，需 .NET Framework 4.0 运行时，Win7 及以上一般已内置）
3. 填入目标 IP 和端口，点连接即可收发

> 首次运行若被 SmartScreen / 杀毒软件提示，这是未签名程序的正常提示，选择「更多信息 → 仍要运行」。

## 技术信息

| 项目 | 值 |
|---|---|
| 程序集 | `TcpDebug.exe`（.NET / WinForms） |
| 版本 | v2.0.0 |
| 大小 | 40,448 字节 |
| SHA-256 | `c16133c3ca283f2508b1def603d5bf4cd18545600612e609f876bdab47d99441` |

## 关于二进制文件

本目录的 `TCP-Debug-Assistant.exe` 由 `.github/workflows/materialize-tcp-debug.yml` 从
`TCP-Debug-Assistant.exe.b64` 在 CI 中无损解码生成。保留 base64 源文件是为了让二进制
能通过纯文本方式安全地提交与审计；解码后 SHA-256 与原始文件一致。
