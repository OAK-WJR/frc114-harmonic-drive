# frc114-harmonic-drive

[![许可: CERN-OHL-S-2.0](https://img.shields.io/badge/License-CERN--OHL--S--2.0-blue.svg)](./LICENSE)
[![English](https://img.shields.io/badge/lang-EN-black)](./README.md)
[![搜索本仓库](https://img.shields.io/badge/%F0%9F%94%8E_搜索-打开搜索页-brightgreen)](https://OAK-WJR.github.io/frc114-harmonic-drive/search.html)

> 说明：出于安全原因，GitHub 的 README **不支持交互式搜索框/脚本**。  
> 想要真正可输入的搜索框，请使用上面的 **搜索页**（GitHub Pages）。

---

## 亮点
- 面向 FRC 的谐波减速器 CAD：**基础减速器**、**电机连接板适配器**、**通用关节（垂直/并行）**。
- **每个型号只有一个 AJI**（如 D25）：同型号下 **所有适配器** 必须与 **所有关节** 通过同一 **AJI** 完全互配。
- **仅 `.step`**：全库统一毫米（mm）、Z↑。

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/design_reference/D25-MotorBoardAdapter_front-example.png">
    <img src="docs/design_reference/D25-MotorBoardAdapter_front-example.png" alt="D25 Motor Board Adapter - 正面" width="45%">
  </picture>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/design_reference/D25-MotorBoardAdapter_back-example.png">
    <img src="docs/design_reference/D25-MotorBoardAdapter_back-example.png" alt="D25 Motor Board Adapter - 背面" width="45%">
  </picture>
</p>

---

## 快速搜索“芯片”
- 型号： [D17](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+D17&type=code) · [D20](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+D20&type=code) · [D25](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+D25&type=code) · [D32](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+D32&type=code) · [J32](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2F+J32&type=code)
- 电机： [NEOVERTEX](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fadapters+NEOVERTEX&type=code) · [NEO](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fadapters+NEO&type=code) · [KRAKENX60](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fadapters+KRAKENX60&type=code) · [FALCON500](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fadapters+FALCON500&type=code)
- 关节： [vertical 垂直](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fjoints%2Fvertical+vertical&type=code) · [parallel 并行](https://github.com/OAK-WJR/frc114-harmonic-drive/search?q=path%3Amechanical%2Fjoints%2Fparallel+parallel&type=code)

---

## 目录结构
```
mechanical/
  base_reducers/
  adapters/                     # <Series><Frame>/<Series><Frame>-<MOTOR>-<vN>[-<Mount>].step
  joints/                       # vertical/parallel/<Series><Frame>-<type>.step
docs/
  design_reference/
  usage.md
config/
LICENSE
```

## 命名
**基础减速器**
```
<Series><Frame>[-<Ratio>].step     例：D25-24.step，J32.step
```
**适配器**
```
adapters/<Series><Frame>/<Series><Frame>-<MOTOR>-<vN>[-<Mount>].step
MOTOR 全大写：NEOVERTEX/NEO/KRAKENX60/FALCON500；vN：v1/v2/v5；Mount（可选）：P/NT/NF
```
**通用关节**
```
joints/<type>/<Series><Frame>-<type>.step   # type: vertical | parallel
```

## AJI（适配器–关节统一接口）
- 字段：`pilot_d`、`pilot_depth`、`bcd_d`、`holes_n`、`hole_d`、`face_thk`、`datum`；可选：`OD/ID/length`。
- 刚性要求：同型号 **全互配**；**仅通过 AJI** 对接；更换电机/关节时另一侧**无需改图**。
- 参考：`docs/design_reference/D25-MotorBoardAdapter-example.step`（含正/背面示意图）。

## 贡献
1) Onshape 建模 → 导出 `.step`（mm、Z↑）。  
2) 按规则命名与入库。  
3) 与同型号对侧件完成全互配测试。  
4) （可选）更新 `config/variants.csv`。  
5) PR 附 1–2 张截图。

## 第三方参考模型
厂商“仅供参考（reference‑only）” STEP **不随仓库发布**；请本地参考厂商链接。仓库仅发布自建包络与 AJI 规范。

## 许可
© 2025 Jiarui Wu · **CERN‑OHL‑S v2.0**。详见 [LICENSE](./LICENSE)。  
SPDX：`CERN-OHL-S-2.0`
