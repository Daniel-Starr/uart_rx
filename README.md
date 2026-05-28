# uart_rx — USART1 发送示例

基于 STM32F103C8T6（Blue Pill）的 UART 发送演示项目，启动时通过 USART1 发送测试字符和字符串。

## 硬件平台

- **MCU:** STM32F103C8T6 (Cortex-M3, LQFP48)
- **开发板:** Blue Pill
- **时钟:** 8MHz HSI
- **开发环境:** Keil MDK-ARM V5.32

## 外设使用

| 外设 | 配置 | 引脚 |
|------|------|------|
| USART1 | 115200 8N1 | PA9 (TX) / PA10 (RX) |
| GPIO | PC13 推挽输出 | 板载 LED（未使用） |

## 功能说明

程序启动后执行一次性发送：

1. 发送单字符 `'a'`
2. 发送字符串 `"hello word\r\n"`

使用阻塞模式 `HAL_UART_Transmit`，发送完成后主循环空转。

## 备注

- 代码中包含注释掉的 HEX 发送示例（0x5A、字节数组）
- PC13 GPIO 已配置但未在代码中操作
- 项目名含 "rx" 但实际只有 TX 功能，适合作为 UART 发送学习参考
