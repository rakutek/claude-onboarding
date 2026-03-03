# Step 07: Skills の概念理解

## 目標

Claude Code の Skills（スキル）機能を理解し、実際にスキルを使ってみる。

## Skills とは

Skills は、Claude Code に特定の能力やワークフローを追加する仕組みです。`/スキル名` で呼び出すことができます。

```
ユーザー: /check-setup
        ↓
Claude Code: .claude/skills/check-setup/SKILL.md を読み込む
        ↓
SKILL.md の指示に従って実行
        ↓
結果を表示
```

## SKILL.md の構造

スキルは `.claude/skills/スキル名/SKILL.md` に配置します。

```markdown
---
name: スキル名
description: スキルの説明。どんな時に呼び出されるかも記述。
---

# スキルのタイトル

スキルの実行手順をここに記述。
Claude はこの指示に従って動作する。
```

### frontmatter（`---` で囲まれた部分）

| フィールド | 説明 |
|-----------|------|
| `name` | スキルの識別名 |
| `description` | スキルの説明。自然言語のトリガー条件も記述 |

### 本文

Claude が実行する手順を Markdown で記述します。Bash コマンドや手順を具体的に書くことで、Claude が正確に実行できます。

## スキルの配置場所

| 場所 | 適用範囲 |
|------|---------|
| `~/.claude/skills/` | すべてのプロジェクトで使える |
| `プロジェクト/.claude/skills/` | そのプロジェクトでのみ使える |

## このチュートリアルのスキル

このチュートリアルには3つのスキルが含まれています：

| スキル | ファイル | 機能 |
|--------|---------|------|
| `/check-setup` | `.claude/skills/check-setup/SKILL.md` | 環境の状態チェック |
| `/setup-mcp` | `.claude/skills/setup-mcp/SKILL.md` | MCP 設定ガイド |
| `/next` | `.claude/skills/next/SKILL.md` | チュートリアル進行 |

## やってみよう

1. `/check-setup` を実行して、環境の状態を確認してみましょう
2. `.claude/skills/check-setup/SKILL.md` のファイルを読んで、スキルの中身を確認してみましょう
   ```
   .claude/skills/check-setup/SKILL.md を読んで
   ```
3. スキルの `description` がどのように使われているか理解しましょう

## 確認チェック

- [ ] `/check-setup` を実行して結果が表示された
- [ ] SKILL.md の構造（frontmatter + 本文）を理解した
- [ ] スキルの配置場所によって適用範囲が変わることを理解した
