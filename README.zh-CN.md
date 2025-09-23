# frc114-harmonic-drive

[![许可: CERN-OHL-S-2.0](https://img.shields.io/badge/License-CERN--OHL--S--2.0-blue.svg)](./LICENSE)
[**🔎 搜索模型**](http://34.61.86.245/docs/search.html) · [**📘 文档**](http://34.61.86.245/docs/) · [English](./README.md)

> 面向 FRC 机器人：**谐波减速器**、电机连接板 **适配器**、**通用关节**（垂直/并行）的模块化 CAD 库。  
> 全库只接受 **`.step`**（单位 mm，坐标 Z↑）。

<p align="center">
  <img src="docs/design_reference/D25-MotorBoardAdapter_front-example.png" width="45%" alt="D25 适配器 - 正面"/>
  <img src="docs/design_reference/D25-MotorBoardAdapter_back-example.png"  width="45%" alt="D25 适配器 - 背面"/>
</p>

---

## 为什么做这个库

- **每个型号一套 AJI**（例如 **D25**）：该型号下**所有适配器**必须与**所有关节**通过同一 **AJI** 互配。  
- **易换装**：更换电机或关节时，另一侧**无需重画**。  
- **统一导出**：只用 `.step`，保证跨 CAD 兼容。

---

## 快速搜索

- 型号： [D17](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+D17&type=code) · [D20](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+D20&type=code) · [D25](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+D25&type=code) · [D32](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+D32&type=code) · [J32](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+J32&type=code)  
- 电机： [NEOVERTEX](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fadapters+NEOVERTEX&type=code) · [NEO](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fadapters+NEO&type=code) · [KRAKENX60](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fadapters+KRAKENX60&type=code) · [FALCON500](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fadapters+FALCON500&type=code)  
- 关节： [vertical 垂直](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fjoints%2Fvertical+vertical&type=code) · [parallel 并行](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fjoints%2Fparallel+parallel&type=code)

> 需要**可输入**的搜索框？使用搜索页 → http://34.61.86.245/docs/search.html

---

## 仓库包含

```
mechanical/
  base_reducers/                # 仅减速器本体（.step）
  adapters/                     # <Series><Frame>/<Series><Frame>-<MOTOR>-<vN>[-<Mount>].step
  joints/                       # vertical|parallel/<Series><Frame>-<type>.step
docs/
  design_reference/             # AJI 示例 step 与配图（正/背面）
  usage.md                      # 完整建模与命名规则
LICENSE
```

**支持型号**：`D17 · D20 · D25 · D32 · J32`  
**示例**：`mechanical/joints/vertical/D25-vertical.step`

---

## 命名（简版）

- **减速器**：`<Series><Frame>[-<Ratio>].step` → `D25-24.step`，`J32.step`  
- **适配器**：`adapters/<Series><Frame>/<Series><Frame>-<MOTOR>-<vN>[-<Mount>].step`  
  - `MOTOR` 全大写：`NEOVERTEX | NEO | KRAKENX60 | FALCON500 | 775PRO`  
  - `vN`：`v1/v2/v5...`；`Mount`（可选）：`P | NT | NF`  
- **通用关节**：`joints/<type>/<Series><Frame>-<type>.step`（type = `vertical | parallel`）

完整规则 → **文档**：http://34.61.86.245/docs/usage.html

---

## AJI（适配器–关节统一接口）

每个型号仅一套 AJI。必备字段：  
`pilot_d`、`pilot_depth`、`bcd_d`、`holes_n`、`hole_d`、`face_thk`、`datum`（可选包络 `OD/ID/length`）。  
刚性要求：**同型号全互配** · **仅通过 AJI 对接** · **可热插拔更换电机/关节**。  
参考文件 → `docs/design_reference/`。

---

## 贡献

1. 导出 **`.step`**（mm，Z↑）。  
2. 按命名与目录放置。  
3. 与同型号对侧件完成 AJI 互配验证。  
4. （可选）更新 `config/variants.csv`。  
5. 提交 PR，并附 1–2 张截图。

---

## 许可与鸣谢

© 2025 Jiarui Wu — 许可：**CERN‑OHL‑S v2.0**（见 `LICENSE`）。  
厂商“仅供参考（reference‑only）”模型不随仓库发布，请在本地引用厂商链接。
