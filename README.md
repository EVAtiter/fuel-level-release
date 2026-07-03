# Fuel Level

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
| 配布 | Mac App Store | 公証済みバイナリ（直接配布）／Homebrew |

バッテリー温度計と消費電力計は非公開 API（バッテリーの内部温度取得 / IOReport）を
使用するため、App Store 版には搭載できません。Plus 版は Developer ID 署名 + Apple
公証済みで配布しています。

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

Fuel Level（無料・燃料計のみ）は Mac App Store で近日公開予定です。

---

## 主な機能

- **燃料計**: 空きメモリ量を自動車の燃料計スタイルで表示（メモリープレッシャーで警告灯が点灯/点滅）
- **バッテリー温度計**（Plus 限定）: バッテリー温度を水温計スタイルで表示
  （対数目盛り、温度しきい値で警告灯が点灯/点滅）
- **消費電力計**（Plus 限定）: SoC の消費電力を燃料計スタイルで表示
  （直近 5 分のピークを 100% とする相対表示、ピーク更新中は警告灯が点滅）
- ウインドウモード（通常 / 常に最前面 / ウィジェット）
- 表示色（自動 / Day / Night）
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
| Distribution | Mac App Store | Notarized binary (direct) / Homebrew |

The battery thermometer and power meter rely on undocumented APIs (reading
the battery's internal temperature / IOReport) and cannot be included in the
App Store build. The Plus edition is Developer ID signed and notarized by Apple.

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

Fuel Level (free, fuel gauge only) is coming soon to the Mac App Store.

---

## Features

- **Fuel gauge**: shows available memory as a car-style fuel gauge (a
  warning lamp lights/blinks under memory pressure)
- **Battery thermometer** (Plus only): shows battery temperature as a
  car-style coolant gauge (logarithmic scale, a warning lamp lights/blinks
  past temperature thresholds)
- **Power meter** (Plus only): shows SoC power draw as a car-style fuel gauge
  (relative to the peak over the last 5 minutes; the warning lamp blinks while
  a new peak is being set)
- Window modes (normal / always on top / widget)
- Appearance (auto / Day / Night)
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
