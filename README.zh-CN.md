# frc114-harmonic-drive

[![许可: CERN-OHL-S-2.0](https://img.shields.io/badge/License-CERN--OHL--S--2.0-blue.svg)](./LICENSE)
[**🔎 搜索模型**](http://34.61.86.245/docs/search.html) · [**📘 文档**](http://34.61.86.245/docs/) · [English](./README.md)

> 面向 FRC 机器人：**谐波减速器**、减速器的frc电机 **适配器**、**通用关节**的模块化库。  
> 全库仅接受 **`.step`**（单位 mm，坐标 Z↑）。

<!-- 顶部左右：实物 + joint 主视渲染 -->
<p align="center">
  <img src="docs/real-pictures/real-joint-D25_vertical_top.png" width="49%" alt="实物装配 - D25 垂直关节（俯视）"/>
  <img src="docs/design-example/pictures/joint-D25_vertical_main.png" width="49%" alt="D25 垂直关节 - 主视渲染"/>
</p>

---

## 为什么做这个库

- **每个型号一套 AJI**（如 **D25**）：同型号**所有适配器**必须与**所有关节**通过同一 **AJI** 互配。  
- **易换装**：更换电机或关节时，另一侧**无需重画**。  
- **统一导出**：只用 `.step`，保证跨 CAD 兼容。

---

## 快速搜索（当前已有）

- 型号： [D17](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+D17&type=code) · [D20](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+D20&type=code) · [D25](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+D25&type=code) · [J32](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+J32&type=code)  
- 电机： [NEOVERTEX](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fadapters+NEOVERTEX&type=code) · [KRAKENX60](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fadapters+KRAKENX60&type=code)  
- 关节： [vertical（全部）](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fjoints+vertical&type=code) · [仅 D25-vertical](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fjoints+%22D25-vertical%22&type=code)

> 需要**可输入**的搜索框？用 **搜索页** → http://34.61.86.245/docs/search.html

---

## 仓库结构

mechanical/
base_reducers/ # 仅减速器本体（.step）
adapters/ # <Series><Frame>/<Series><Frame>-<MOTOR>-<vN>[-<Mount>].step
joints/ # <Series><Frame>-vertical.step
docs/
design-example/
D25-MotorBoardAdapter_example-design_reference.step
pictures/ # 本 README 使用的配图
real-pictures/ # 实物照片
LICENSE

**当前支持型号**：`D17 · D20 · D25 · J32`  
**示例**：`mechanical/joints/D25-vertical.step`

---

## 命名（简版）

- **减速器**：`<Series><Frame>[-<Ratio>].step` → `D25-24.step`，`J32.step`  
- **适配器**：`adapters/<Series><Frame>/<Series><Frame>-<MOTOR>-<vN>[-<Mount>].step`  
  - `MOTOR` 建议全大写：`NEOVERTEX | KRAKENX60 | ...`  
  - `vN`：`v1/v2/v5...`；`Mount`（可选）：`P | NT | NF`  
  - *说明*：旧文件可能有大小写混用，后续会逐步统一。  
- **通用关节**：`joints/<Series><Frame>-vertical.step`

完整规则 → **文档**：http://34.61.86.245/docs/usage.html

---

## 贡献 / 要求

1. 仅导出 **`.step`**（mm，Z↑）。  
2. 按命名/目录放置。  
3. 与同型号对侧件完成 AJI 互配验证。  
4. （可选）更新 `config/variants.csv`。  
5. 提交 PR 并附 1–2 张截图。

<!-- 底部左右：设计参考（蓝色区域不可修改） -->
<p align="center">
  <img src="docs/design-example/pictures/D25-MotorBoardAdapter_back-design_reference.png" width="49%" alt="D25 适配器 - 背面（蓝色为 AJI 冻结区）"/>
  <img src="docs/design-example/pictures/D25-MotorBoardAdapter_front-design_reference.png" width="49%" alt="D25 适配器 - 正面"/>
</p>
<p align="center"><i>蓝色区域 = AJI 配合/基准区（冻结，不可修改）。</i></p>

---

## 许可与鸣谢

© 2025 Jiarui Wu — 许可：**CERN-OHL-S v2.0**（见 `LICENSE`）。  
厂商“reference-only”模型不随仓库发布，请在本地引用厂商链接。
