---
name: setup-mcp
description: MCP コネクタの設定をインタラクティブにガイドするスキル。「MCP設定」「コネクタ設定」「/setup-mcp」で呼び出されます。引数でサーバー名を指定できます（例：/setup-mcp chrome-devtools）。
---

# MCP セットアップガイドスキル

MCP（Model Context Protocol）サーバーの設定をインタラクティブにガイドします。

## 対応サーバー

### Chrome DevTools MCP

Chrome ブラウザの DevTools に接続し、ページの操作・スクリーンショット・コンソール確認などを行えるようにします。

**セットアップコマンド：**

```bash
claude mcp add chrome-devtools --scope user -- npx -y chrome-devtools-mcp@latest
```

> `npx` は Node.js に付属のパッケージランナーです。`-y` オプションで確認なしにパッケージを実行できます。

**使用前の準備：**
1. Chrome を起動する
2. `chrome://flags/#allow-remote-debugging` を有効にする（または `--remote-debugging-port=9222` 付きで起動する）

### その他のコネクタ（Claude アプリ側）

以下のコネクタは Claude アプリ（Web/デスクトップ）の設定画面から有効化します：

| コネクタ | 説明 | 設定場所 |
|---------|------|---------|
| Google Drive | ドキュメント・スプレッドシート参照 | Claude アプリ → 設定 → コネクタ |
| Notion | ページ・データベース参照 | Claude アプリ → 設定 → コネクタ |
| Slack | チャンネル・メッセージ参照 | Claude アプリ → 設定 → コネクタ |

## 進行フロー

1. ユーザーに設定したいサーバーを確認する
2. 対応するセットアップ手順を案内する
3. セットアップ後、`claude mcp list` で接続を確認する
4. 問題があれば、トラブルシューティングを案内する
