# Hi, I'm ccwings007 👋

**FPGA 开发工程师** · 5G 基带数字前端 · 多通道高速数据采集

![Verilog](https://img.shields.io/badge/Verilog-1976D2?style=flat-square) ![Vivado](https://img.shields.io/badge/Vivado-EF6C00?style=flat-square) ![Xilinx 7 Series](https://img.shields.io/badge/Xilinx_7_Series-00796B?style=flat-square) ![PCIe XDMA](https://img.shields.io/badge/PCIe_XDMA-6A1B9A?style=flat-square) ![Python](https://img.shields.io/badge/Python-388E3C?style=flat-square) ![DeepSeek](https://img.shields.io/badge/DeepSeek-4D6BFE?style=flat-square)

> 习惯把「仿真能过」推进到「板子上指标能达标」。

## 🧭 关于我

2021 年至今从事 FPGA 逻辑设计与板级调试，两条主线：**无线通信基站数字前端（DFE）** 与 **多通道高速数据采集**。两者共同点是对吞吐、时延与确定性要求极高，也是我最熟悉的工作区间。

- **通信** —— NR/LTE 的 DUC/DDC、DPD/CFR、Lowphy；eCPRI / CPRI 链路、JESD204B 高速转换器接口、级联组网
- **采集** —— 多通道同步采集、位切片累加压缩、板内缓冲、PCIe XDMA 直传与主机侧对账
- **主机侧** —— 自研调试分析台 LinkScope，形成「FPGA ⇄ 主机」双侧闭环
- **工作方式** —— 模块设计 → testbench 功能与时序仿真 → 板级调试 → 配合算法与硬件收敛 EVM、ACPR、时延
- **AI 辅助** —— 以 DeepSeek 为主力模型，用于 RTL 审查、脚本与文档；产出视为草稿，须过仿真或实测验收

## 🛠 技术栈

- **HDL / 验证** —— Verilog、Testbench、时序约束、ModelSim、Verilator
- **器件平台** —— Zynq UltraScale+（XCZU11EG）、Zynq-7000（XC7Z100 / XC7Z035）、Artix-7、Altera
- **无线通信 / DSP** —— DUC/DDC、DPD、CFR、FFT / FIR / CIC、eCPRI、CPRI、JESD204B
- **高速接口** —— PCIe XDMA、Aurora 8B10B、GTP / GTH、AXI4 / Stream、Avalon、LVDS、Ethernet、IIC / SPI / UART
- **工具链** —— Vivado、Quartus、Vitis、MATLAB、Python、C / C++、Tcl、Git、Linux / WSL
- **仪器** —— 频谱仪、信号源、示波器、逻辑分析仪

## 🚀 正在做 / 负责

### PXIe-8EP · 多通道高速数据采集（当前主线）

8 卡 32 通道同步采集与实时上传：`2× ADC3668 (LVDS, 225 MSPS)` → `位切片累加 ×4096` → `弹性 FIFO` → `PCIe Gen2 x4 / XDMA` → `主机侧落盘`

3U PXIe 单槽宽，XC7Z035，131072 bin/通道/趟（Δt ≈ 0.61 ps）；验收 12 轮 FULL 12 / SHORT 0 / DEAD 0，卡侧 `df_drop = 0`。

### LinkScope · 采集链调试分析台（自研，代码未公开）

主机侧 Web 工具，PXIe / UDP 双数据源，在波形 · S 参数（SDD11 / SDD21）· TDR 三层定位问题。零依赖 Python 后端配 1.3 MB 单文件自绘 SVG 前端，支持 EP 帧回放无板联调与分层自动化回归，经 Nuitka + Inno Setup 打包为免装 Python 的安装包。

### 过往项目

- **Aurora 三级架构**（已归档）—— 16 采集 + 4 缓存 + 1 主控 FPGA，Aurora 2.5 Gbps over GTP，千兆 UDP 回传；采集侧 DDR3 缓冲，其余纯 BRAM 透传
- **无线通信** —— 4G/5G 一体化基站 / 车载 / 应急基站，NR/LTE 数字前端 DUC/DDC、DPD/CFR、Lowphy、eCPRI 与 JESD204B 链路

### 在学

PCIe 多队列调度与 XDMA 描述符链优化 · 时序收敛（CDC 约束、False Path 边界）· 数据通路的形式化与随机化验证

## 📫 联系方式

| 渠道 | 地址 |
|---|---|
| GitHub | [@ccwings007](https://github.com/ccwings007) |
| Gitee | [@ccwings007](https://gitee.com/ccwings007) |
| Email | <bog007@qq.com> |

> 关于 FPGA 逻辑设计、无线通信数字前端或高速接口的问题，欢迎通过 Issue 或邮件交流。

<details>
<summary><b>English (short)</b></summary>

FPGA engineer with 5 years of experience across two domains: **digital front-end (DFE) for 4G/5G base stations** and **multi-channel high-speed data acquisition**.

- Radio: DUC/DDC, DPD/CFR, Lowphy, eCPRI / CPRI links, JESD204B converters, cascaded network bring-up
- Acquisition: synchronous multi-channel sampling, bit-sliced accumulation, PCIe XDMA streaming to host
- **LinkScope** (self-built, source not public): a PXIe/UDP capture-debug workbench — zero-dependency Python backend, single-file SVG front-end, waveform / S-parameter / TDR analysis, packaged with Nuitka + Inno Setup
- Devices: Zynq UltraScale+ (XCZU11EG), Zynq-7000 (XC7Z100 / XC7Z035), Artix-7
- Toolchain: Vivado, Quartus, ModelSim, Verilator, MATLAB, Vitis; Python / C for host-side tooling
- AI-assisted workflow: **DeepSeek** as the primary model for RTL review, testbench and script generation, documentation and debug triage — every AI output is treated as a draft and must pass simulation or on-board verification before merge

Reach me at **<bog007@qq.com>**.

</details>
