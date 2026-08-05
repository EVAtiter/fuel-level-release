# Fuel Level

<img width="1280" height="340" alt="1280" src="https://github.com/user-attachments/assets/afa717a9-a2ec-4c5e-aa1a-cf456f7e2125" />

**Fuel Level** は、macOS の空きメモリを自動車の燃料計で表示するメニューバー常駐アプリです。
1995 年に発表した Classic Mac OS 版 C アプリを、SwiftUI で全面リニューアルしました。

このリポジトリは Fuel Level の **配布・サポート窓口**です。ソースコードは公開していません。

---

## 2 つの配布版

| | Fuel Level（Mac App Store） | Fuel Level Plus（このリポジトリ） |
|---|---|---|
| 燃料計（空きメモリ） | ✅ | ✅ |
| バッテリー温度計 | ― | ✅ |
| 消費電力計 | ― | ✅ |
| システムモニター | ✅ CPU のみ | ✅ CPU + 消費電力 + GPU / Neural Engine |
| 画面下端で呼び出す | ✅ | ✅ |
| スタイル・照明・ウインドウモード | ✅ | ✅ |
| 配布 | Mac App Store | 公証済みバイナリ（直接配布）／Homebrew |

バッテリー温度計・消費電力計と、システムモニターの GPU / Neural Engine / 消費電力の
表示は、非公開 API（バッテリーの内部温度取得 / IOReport）を使用するため App Store 版
には搭載できません。App Store 版のシステムモニターは、公開 API だけで取得できる
**CPU 使用率の時系列**として動きます。

Plus 版は Developer ID 署名 + Apple 公証済みで配布しています。

---

## ダウンロード（Fuel Level Plus）

### Homebrew

```
brew install --cask EVAtiter/tap/fuel-level-plus
```

### 直接ダウンロード

最新版は [Releases](https://github.com/EVAtiter/fuel-level-release/releases/latest) から。

1. `Fuel-Level-Plus-<バージョン>.zip` をダウンロード
2. 解凍して `Fuel Level Plus.app` を `アプリケーション` フォルダーへ
3. 初回起動時に確認が出たら「開く」をクリック（公証済みなので Gatekeeper を通ります）

## Mac App Store 版

Fuel Level（無料・燃料計とシステムモニター）は Mac App Store で公開しています。

https://apps.apple.com/app/fuel-level/id6786531692

---

## 主な機能

### 計器

- **燃料計**: 空きメモリ量を自動車の燃料計スタイルで表示（メモリープレッシャーで警告灯が点灯/点滅）
- **バッテリー温度計**（Plus 限定）: バッテリー温度を水温計スタイルで表示。
  10〜80℃ を**対数目盛り**にしてあります。これは幅広い温度範囲を 1 つの文字盤で
  視覚的に有効に表現するためで、目盛りは 10・20・40・80℃ と倍々に並びます。
  針が真上を指すのは 20℃ と 40℃ の幾何学的な中心 √(20×40) ≈ 28.3℃ であり、
  算術平均の 30℃ ではありません。温度しきい値で警告灯が点灯/点滅します
- **消費電力計**（Plus 限定）: SoC の消費電力を燃料計スタイルで表示。期間を区切らず
  観測した最大値を 100% とする相対表示で、ピーク更新中は警告灯が点滅します。記憶した
  ピーク値はメニューの「消費電力ピーク記憶をリセット」でいつでもリセットできます
- **システムモニター**: 使用状況の推移を、自動車のメーターパネル風のキューブを積み上げた
  横長パネルで表示します（既定は非表示）。
  Plus 版は CPU 使用率（琥珀＝ユーザー、緑＝システム）と消費電力（紫）を重ね、
  右端に GPU（シアン）と Neural Engine（ピンク）の使用率ゲージを並べます。ゲージは
  0 / 50 / 100% にあたる段がオフホワイトになり、目盛りとして読めます。
  App Store 版は CPU 使用率の時系列のみで、そのぶんグラフが横いっぱいに広がります
- **数値表示**: システムモニターをクリックすると、グラフと数値が入れ替わります。
  桁の位置が固定された数字で、空きメモリ・メモリープレッシャー・CPU（ユーザーと
  システムの内訳つき）が読めます。Plus 版ではバッテリー温度・消費電力・GPU /
  Neural Engine も並びます

### 見た目・操作

- **スタイル**: コンフォート（下端が欠けた形）／スポーツ（真円）
- **画面下端で呼び出す**: マウスカーソルを画面の下端にしばらく当てると、ほかのウインドウに
  隠れている計器がまとめて手前に出てきます（既定はオフ）。呼び出している間だけ、
  システムモニターは選んでいるのと逆の表示（グラフ ⇄ 数値）になります
- **常に最前面**: 計器をすべてのウインドウより手前に置きます
- **壁紙に貼り付ける**: 計器を壁紙にピン留めします（クリックは下のウインドウへ抜けます）
- **照明**: 自動 / Day / Night
- 日本語 / 英語 UI 対応
- アプリ自身は外部通信を一切行いません

## 動作要件

- macOS 14.0 Sonoma 以降
- Apple Silicon 専用（Intel Mac 非対応）
- バッテリー温度計はバッテリー搭載機（ノート型 Mac）のみ表示されます
- 消費電力計は Apple Silicon（IOReport による SoC 消費電力取得）で表示されます

## プライバシー

Fuel Level は **データを一切収集しません**。詳細は [PRIVACY.md](PRIVACY.md) を参照してください。

## サポート

質問・要望・不具合報告は [Issues](https://github.com/EVAtiter/fuel-level-release/issues) へ。

日本語・英語どちらでも歓迎です。

---

# Fuel Level (English)

**Fuel Level** is a macOS menu bar utility that displays your available
memory as a car fuel gauge. It's a full SwiftUI rewrite of a Classic Mac OS
C app originally released in 1995.

This repository is the **distribution and support channel** for Fuel Level.
Source code is not published here.

---

## Two distributions

| | Fuel Level (Mac App Store) | Fuel Level Plus (this repo) |
|---|---|---|
| Fuel gauge (free memory) | ✅ | ✅ |
| Battery thermometer | — | ✅ |
| Power meter | — | ✅ |
| System Monitor | ✅ CPU only | ✅ CPU + power + GPU / Neural Engine |
| Quick Reveal | ✅ | ✅ |
| Style, lighting, window modes | ✅ | ✅ |
| Distribution | Mac App Store | Notarized binary (direct) / Homebrew |

The battery thermometer, the power meter, and the GPU / Neural Engine / power
layers of the System Monitor rely on undocumented APIs (reading the battery's
internal temperature / IOReport) and cannot be included in the App Store build.
The App Store edition's System Monitor shows **CPU usage over time**, which
public APIs can provide.

The Plus edition is Developer ID signed and notarized by Apple.

## Download (Fuel Level Plus)

### Homebrew

```
brew install --cask EVAtiter/tap/fuel-level-plus
```

### Direct download

Get the latest version from
[Releases](https://github.com/EVAtiter/fuel-level-release/releases/latest).

1. Download `Fuel-Level-Plus-<version>.zip`
2. Unzip and move `Fuel Level Plus.app` to your `Applications` folder
3. On first launch, click "Open" if prompted (the app is notarized, so
   Gatekeeper will allow it)

## Mac App Store edition

Fuel Level (free — fuel gauge and System Monitor) is on the Mac App Store.

https://apps.apple.com/app/fuel-level/id6786531692

---

## Features

### Gauges

- **Fuel gauge**: shows available memory as a car-style fuel gauge (a
  warning lamp lights/blinks under memory pressure)
- **Battery thermometer** (Plus only): shows battery temperature as a
  car-style coolant gauge. The 10–80 °C range uses a **logarithmic scale** so
  that a wide temperature range reads usefully on a single dial: the ticks run
  10, 20, 40, 80 °C, doubling each step. The needle points straight up at the
  geometric midpoint of 20 and 40 °C — √(20×40) ≈ 28.3 °C — not the arithmetic
  mean of 30 °C. A warning lamp lights/blinks past temperature thresholds
- **Power meter** (Plus only): shows SoC power draw as a car-style fuel gauge,
  relative to the observed maximum (100%), which is remembered indefinitely.
  The warning lamp blinks while a new peak is being set. The remembered peak
  can be reset anytime from the "Reset Power Peak Memory" menu item
- **System Monitor**: a wide panel that plots usage over time as stacked cubes,
  styled after a car instrument panel (hidden by default).
  The Plus edition overlays CPU usage (amber = user, green = system) with power
  draw (purple), and adds GPU (cyan) and Neural Engine (pink) gauges on the
  right; the rows at 0 / 50 / 100% turn off-white and read as a scale.
  The App Store edition plots CPU usage only, so the graph spans the full width
- **Numeric readout**: click the System Monitor to switch between the graph and
  figures. Fixed-width digits show free memory, memory pressure and CPU (broken
  down into user and system time); the Plus edition adds battery temperature,
  power draw and GPU / Neural Engine

### Look and handling

- **Style**: Comfort (the original flat-bottomed shape) or Sport (a full circle)
- **Quick Reveal**: rest the pointer at the bottom edge of the screen for a
  moment and any gauges hidden behind other windows come forward together
  (off by default). While it holds, the System Monitor shows the opposite of
  what you selected (graph vs. figures)
- **Always on Top**: keeps the gauges in front of every other window
- **Pin to Wallpaper**: pins the gauges to the desktop wallpaper (clicks pass
  through to the window underneath)
- **Lighting**: auto / Day / Night
- Japanese / English UI
- The app never communicates over the network

## Requirements

- macOS 14.0 Sonoma or later
- Apple Silicon only (Intel Macs are not supported)
- The battery thermometer only appears on Macs with a battery (notebooks)
- The power meter reads SoC power draw via IOReport (Apple Silicon)

## Privacy

Fuel Level **collects no data**. See [PRIVACY.md](PRIVACY.md) for details.

## Support

Questions, feature requests, and bug reports:
[Issues](https://github.com/EVAtiter/fuel-level-release/issues).

Japanese and English are both welcome.
