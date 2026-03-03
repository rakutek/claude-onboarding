# Step 02: MCP（コネクタ）の設定

## 目標

MCP（Model Context Protocol）の概念を理解し、Claude アプリでコネクタを設定する。

## MCP とは

MCP は、Claude が外部のツールやデータソースに接続するための統一プロトコルです。

```
Claude ←→ MCP プロトコル ←→ 外部サービス（Google Drive, Slack, Notion 等）
```

従来はサービスごとに個別の連携方法が必要でしたが、MCP によって統一的なインターフェースで接続できます。

## コネクタ（Claude アプリ側の MCP）

Claude アプリ（Web / デスクトップ）では、「コネクタ」という名前で MCP が提供されています。

### 利用可能なコネクタ

| コネクタ | できること |
|---------|-----------|
| **Google Drive** | ドキュメント、スプレッドシート、スライドの内容を参照 |
| **Notion** | ページ、データベースの内容を参照 |
| **Slack** | チャンネルのメッセージ、スレッドを参照・送信 |

### コネクタと Claude Code MCP の違い

| | コネクタ | Claude Code MCP |
|---|---------|----------------|
| 設定場所 | Claude アプリの設定画面 | ターミナル（`claude mcp add`） |
| 対象 | SaaS（Slack, Drive 等） | 開発ツール（DevTools, DB 等） |
| 認証 | OAuth（自動） | コマンドラインで設定 |
| 使う場面 | Claude との会話 | Claude Code でのコーディング |

## やってみよう

1. Claude Desktop を開く
2. 左下のアイコン → 「Settings」→「Connected apps」を開く
3. 以下のコネクタから、業務で使うものを有効にする：
   - Google Drive（社内ドキュメント参照用）
   - Notion（社内 Wiki 参照用）
   - Slack（チャンネル参照用）
4. 有効にしたコネクタで実際に試してみる
   - 例：「Slack の #general チャンネルの最新メッセージを教えて」

## 確認チェック

- [ ] コネクタを1つ以上有効にした
- slackでなんとか試し見てる