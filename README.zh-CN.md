# frc114-harmonic-drive

[![许可: CERN-OHL-S-2.0](https://img.shields.io/badge/License-CERN--OHL--S--2.0-blue.svg)](./LICENSE)
[**🔎 按文件名搜索**](https://github.com/OAK-WJR/frc114-harmonic-drive/find/main) · [**📘 文档**](http://34.61.86.245/docs/) · [English](./README.md)

> 面向 FRC 机器人：**谐波减速器**、电机连接板 **适配器**、**通用关节**（垂直）的模块化 CAD 库。  
> 全库仅接受 **`.step`**（单位 mm，坐标 Z↑）。*（旧的非 STEP 文件将逐步迁移）*

<p align="center">
  <img src="docs/real-pictures/real-joint-D25_vertical_top.png" width="49%" alt="实物装配 - D25 垂直关节（俯视）"/>
  <img src="docs/design-example/pictures/joint-D25_vertical_main.png" width="49%" alt="D25 垂直关节 - 主视渲染"/>
</p>

---

## 为什么做这个库

- **每个型号一套 AJI**（如 **D25**）：同型号**所有适配器**与**所有关节**通过同一 **AJI** 互配。  
- **易换装**：更换电机或关节时，另一侧**无需重画**。  
- **统一导出**：只用 `.step`，保证跨 CAD 兼容。

---

## 快速访问

- **按目录浏览**
  - 减速器：[`mechanical/base_reducers/`](https://github.com/OAK-WJR/frc114-harmonic-drive/tree/main/mechanical/base_reducers)
  - 适配器：[`D17`](https://github.com/OAK-WJR/frc114-harmonic-drive/tree/main/mechanical/adapters/D17) · [`D20`](https://github.com/OAK-WJR/frc114-harmonic-drive/tree/main/mechanical/adapters/D20) · [`D25`](https://github.com/OAK-WJR/frc114-harmonic-drive/tree/main/mechanical/adapters/D25) · [`J32`](https://github.com/OAK-WJR/frc114-harmonic-drive/tree/main/mechanical/adapters/J32)
  - 关节：[`mechanical/joints/`](https://github.com/OAK-WJR/frc114-harmonic-drive/tree/main/mechanical/joints)
- **按文件名搜索**（对二进制也有效）：  
  → https://github.com/OAK-WJR/frc114-harmonic-drive/find/main  
  试试：`D25-vertical` · `NEOVertex` · `KrakenX60`

---

## 仓库结构

```text
mechanical/
  base_reducers/                # 仅减速器本体（.step）
  adapters/                     # <Series>/<...MOTOR...>.step
  joints/                       # <Series>-vertical.step
docs/
  design-example/
    D25-MotorBoardAdapter_example-design_reference.step
    pictures/                   # 本 README 配图
  real-pictures/                # 实物照片
LICENSE
```

**当前支持型号**：`D17 · D20 · D25 · J32`  
**示例**：`mechanical/joints/D25-vertical.step`

---

## 命名（简版）

- **减速器**：`<Series><Frame>[-<Ratio>].step` → `D25-24.step`，`J32.step`  
- **适配器**：`adapters/<Series>/<Series>-<MOTOR>-<vN>[-<Mount>].step`  
  - `MOTOR` 建议全大写：`NEOVERTEX | KRAKENX60 | ...`  
  - `vN`：`v1/v2/v5...`；`Mount`（可选）：`P | NT | NF`  
- **通用关节**：`joints/<Series>-vertical.step`

完整规则 → **文档**：http://34.61.86.245/docs/usage.html

---

## 贡献 / 要求

1. 仅导出 **`.step`**（mm，Z↑）。  
2. 按命名/目录放置。  
3. 与同型号对侧件完成 AJI 互配验证。  
4. （可选）更新 `config/variants.csv`。  
5. 提交 PR 并附 1–2 张截图。

<p align="center">
  <img src="docs/design-example/pictures/D25-MotorBoardAdapter_back-design_reference.png" width="49%" alt="D25 适配器 - 背面（蓝色为 AJI 冻结区）"/>
  <img src="docs/design-example/pictures/D25-MotorBoardAdapter_front-design_reference.png" width="49%" alt="D25 适配器 - 正面"/>
</p>
<p align="center"><i>蓝色区域 = AJI 配合/基准区（冻结，不可修改）。</i></p>

---

## 许可与鸣谢

© 2025 Jiarui Wu — 许可：**CERN-OHL-S v2.0**（见 `LICENSE`）。  
厂商“reference-only”模型不随仓库发布，请在本地引用厂商链接。
