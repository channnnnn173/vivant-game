# 暗号パネル（Capacitor プロジェクト）

ゲーム本体は `www/index.html` の1ファイルです。

## 初回セットアップ

必要なもの: Node.js（LTS）。
Android は Android Studio、iOS は Mac と Xcode が必要です。

```bash
npm install
npm i @capacitor/core @capacitor/cli @capacitor/android @capacitor/ios
npx cap add android     # Androidを作る場合
npx cap add ios         # iOSを作る場合（Macのみ）
npx cap sync
```

## 実機・エミュレータで動かす

```bash
npx cap open android    # Android Studio が開く → ▶ で実行
npx cap open ios        # Xcode が開く → ▶ で実行
```

## ゲームを直したとき

`www/index.html` を編集して、次を実行します。

```bash
npx cap sync
```

## 縦向きに固定する

- Android: `android/app/src/main/AndroidManifest.xml` の `<activity ...>` に
  `android:screenOrientation="portrait"` を追加します。
- iOS: Xcode のターゲット > General > Deployment Info で、Device Orientation の
  Portrait 以外のチェックを外します。

## 公開前に変えるもの

- `capacitor.config.json` の `appId`（例: `com.example.angopanel`）は、自分のものに変更します。
  一度ストアに出すと変更できません。
- アプリアイコンと起動画面は、`@capacitor/assets` で一括生成できます。
- アプリ名は `capacitor.config.json` の `appName` です。
