# Step 06: Chrome DevTools MCP の追加

## 目標

Claude Code に Chrome DevTools MCP を追加し、ブラウザ操作が可能な状態にする。

## Chrome DevTools MCP とは

Chrome DevTools MCP を追加すると、Claude Code から直接ブラウザを操作できるようになります。

```
Claude Code → Chrome DevTools MCP → Chrome ブラウザ
                                      ├── ページ操作
                                      ├── スクリーンショット
                                      ├── コンソール確認
                                      └── ネットワーク監視
```

### できること

| 機能 | 例 |
|------|-----|
| ページ操作 | URL を開く、クリック、フォーム入力 |
| スクリーンショット | 表示中のページを画像で取得 |
| コンソール確認 | JavaScript エラーの確認 |
| ネットワーク | API リクエストの監視 |
| パフォーマンス | ページ読み込み速度の測定 |

## セットアップ手順

> **前提条件:** Node.js がインストールされている必要があります。macOS では `brew install node` でインストールできます。

### 1. MCP サーバーを追加

```bash
claude mcp add chrome-devtools --scope user -- npx -y chrome-devtools-mcp@latest
```

- `--scope user`: ユーザースコープ（すべてのプロジェクトで有効）
- `npx -y`: 確認なしで npm パッケージを実行（Node.js 付属）
- `chrome-devtools-mcp@latest`: 常に最新版を使用

### 2. 追加を確認

```bash
claude mcp list
```

`chrome-devtools` が一覧に表示されれば成功です。

### 3. Chrome の準備

Chrome DevTools MCP を使うには、Chrome がデバッグモードで起動している必要があります。

**macOS の場合：**
```bash
/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --remote-debugging-port=9222
```

または、Chrome の設定で有効にする方法もあります。

## やってみよう

1. 以下のコマンドで Chrome DevTools MCP を追加する：
   ```bash
   claude mcp add chrome-devtools --scope user -- npx -y chrome-devtools-mcp@latest
   ```
2. `claude mcp list` で追加されていることを確認する
3. （任意）Chrome をデバッグモードで起動して、Claude Code からスクリーンショットを撮ってみる

## 確認チェック

- [ ] `claude mcp list` に chrome-devtools が表示される
- [ ] `npx` が何をするコマンドか説明できる
- [ ] Chrome DevTools MCP でできることを3つ挙げられる
