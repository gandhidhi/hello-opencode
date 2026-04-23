# Hello OpenCode

このプロジェクトはOpenCodeとGitHubの連携をテストするためのサンプルプロジェクトです。

## 機能

- OpenCode GitHub連携のデモ
- Issue tracking
- Pull Request automation

## セットアップ

### 前提条件
- OpenCode v1.14.20 以上
- GitHub CLI (gh) v2.91.0 以上
- Anthropic API Key (Claude使用のため)

### インストール手順

1. **OpenCodeのインストール**
```bash
curl -fsSL https://opencode.ai/install | bash
export PATH=/Users/yu-suzuki/.opencode/bin:$PATH
```

2. **GitHub CLIのインストールと認証**
```bash
brew install gh
gh auth login
```

3. **OpenCode GitHub連携の設定**
```bash
opencode github install
```

## 使い方

### GitHubでのOpenCode使用

GitHubのIssueやPull Requestで `/opencode` または `/oc` を使用してOpenCodeを呼び出すことができます。

#### 基本的なコマンド例

**Issueでの使用:**
```
/opencode この問題について詳しく説明してください
/oc このバグを修正してください
```

**Pull Requestでの使用:**
```
/opencode このPRをレビューしてください
/oc README.mdにもっと詳細な説明を追加してください
```

### ローカルでのOpenCode使用

```bash
# プロジェクトディレクトリで実行
cd hello-opencode
opencode

# 初期化（初回のみ）
/init
```

## プロジェクト構成

```
hello-opencode/
├── README.md                    # このファイル
├── .github/
│   └── workflows/
│       └── opencode.yml         # GitHub Actions workflow
└── .git/                        # Git repository
```

## GitHub Actions設定

このプロジェクトには、OpenCodeとGitHubを連携するためのGitHub Actionsワークフローが含まれています：

- **トリガー**: Issue comment、PR review comment
- **実行条件**: コメントに `/opencode` または `/oc` が含まれる場合
- **モデル**: `anthropic/claude-sonnet-4-20250514`
- **権限**: 自動的なPR作成、Issue返信が可能

## 連携状況

✅ **Git設定**
- ユーザー名: `gandhidhi`
- メール: `yu-suzuki@kua.kyoto-art.ac.jp`

✅ **GitHub CLI**
- 認証済み: `gandhidhi` アカウント
- プロトコル: HTTPS

✅ **OpenCode**
- バージョン: v1.14.20
- GitHub App: インストール済み

✅ **GitHub リポジトリ**
- URL: https://github.com/gandhidhi/hello-opencode
- GitHub Actions: 有効

## トラブルシューティング

### よくある問題

1. **OpenCodeコマンドが見つからない**
```bash
export PATH=/Users/yu-suzuki/.opencode/bin:$PATH
```

2. **GitHub認証エラー**
```bash
gh auth status
gh auth login  # 再認証が必要な場合
```

3. **API キーの設定**
- GitHubリポジトリの Settings → Secrets and variables → Actions
- `ANTHROPIC_API_KEY` を追加

### 参考リンク

- [OpenCode公式ドキュメント](https://opencode.ai/docs)
- [OpenCode GitHub連携](https://opencode.ai/docs/github/)
- [GitHub CLI公式サイト](https://cli.github.com/)

---

**作成者**: gandhidhi  
**作成日**: 2026年4月23日  
**更新日**: 2026年4月23日