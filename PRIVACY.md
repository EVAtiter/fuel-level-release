# Fuel Level — プライバシーポリシー

**最終更新日**: 2026 年 7 月

## 概要

Fuel Level（以下「本アプリ」といいます）は、ユーザーから一切のデータを収集しません。
個人情報、利用状況、計測値のいずれも、本アプリの開発者および第三者に送信されることは
ありません。

## 収集しない情報

本アプリは以下のいずれの情報も収集・送信しません:

- 氏名、メールアドレス、その他の個人を識別できる情報
- 位置情報
- 連絡先・カレンダー・写真・ファイル等のユーザーデータ
- 利用ログ、クラッシュレポート、解析データ
- アプリが計測した空きメモリ量の数値

## 本アプリが読み取る情報

可視化のために以下の OS 提供 API をローカルで呼び出しますが、得た数値は
画面表示のみに使い、外部に送信しません。

- **空きメモリ量**（燃料計）: `host_statistics64` API（カーネルのメモリ統計を取得）
- **メモリープレッシャー**（警告灯用）: `DispatchSourceMemoryPressure`
  （システムのメモリ逼迫度シグナルを購読）

## ローカル保存

本アプリの設定（ウインドウ位置・表示色・表示モード等）は、お使いの Mac の
**ユーザーごとの設定領域（UserDefaults / App Sandbox コンテナ）にのみ**保存されます。
これらの設定値が外部に送信されることはありません。

## 通信

本アプリ自身は外部サーバーと通信しません。Mac App Store 経由のアプリアップデート時には
Apple の標準的な仕組みが使われますが、これは Apple 社の管理下にあり本アプリの動作には
含まれません。

## 子供の利用

本アプリは特定の年齢層を対象としていませんが、いずれの利用者からも情報を収集しないため、
子供を含むすべての利用者に対して同じ動作をします。

## 連絡先

プライバシーに関する質問は本リポジトリの
[Issues](https://github.com/EVAtiter/fuel-level-release/issues)
までお願いします。

---

# Fuel Level — Privacy Policy

**Last updated**: July 2026

## Overview

Fuel Level (the "App") **collects no data** of any kind. No personal
information, usage data, or measured values are transmitted to the developer
or any third party.

## What we do NOT collect

The App does not collect or transmit any of the following:

- Name, email address, or any personally identifiable information
- Location data
- Contacts, calendars, photos, files, or any user content
- Usage logs, crash reports, or analytics
- The free-memory numbers that the App measures

## What the App reads locally

The App calls the following OS APIs locally for visualization. The values
are used only for on-screen display and are never transmitted externally.

- **Free memory** (fuel gauge): `host_statistics64` (reads kernel memory
  statistics)
- **Memory pressure** (for the warning lamp): `DispatchSourceMemoryPressure`
  (subscribes to the system's memory pressure signal)

## Local storage

App settings (window position, appearance, window mode, etc.) are stored
only in your Mac's per-user preferences area (UserDefaults / App Sandbox
container). These values are never sent off the device.

## Network communication

The App itself does not communicate with any external server. Mac App
Store updates go through Apple's standard mechanism, which is operated by
Apple Inc. and is not part of the App's own behavior.

## Children's use

The App is not directed at any specific age group, but since it collects
no information from any user, it behaves identically for all users,
including children.

## Contact

For privacy-related questions, please use this repository's
[Issues](https://github.com/EVAtiter/fuel-level-release/issues).
