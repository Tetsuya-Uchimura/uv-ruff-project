# uv-ruff-project

uvとRuffを使用したモダンなPython開発環境のテンプレートプロジェクトです。

## 概要

このプロジェクトは、高速なPythonパッケージマネージャー「uv」と、高性能なリンター・フォーマッター「Ruff」を組み合わせた開発環境を提供します。

## 特徴

- ⚡ **uv**: 高速なPythonパッケージマネージャー
- 🔍 **Ruff**: 高性能なリンター・フォーマッター
- 🐍 **Python 3.11+**: 最新のPython機能をサポート
- 📦 **シンプルな構成**: 最小限の設定で開始可能

## プロジェクト構成

```
uv-ruff-project/
├── .devcontainer/          # Dev Container設定
├── .git/                   # Gitリポジトリ
├── .gitignore             # Git無視ファイル
├── .venv/                 # 仮想環境（uv管理）
├── README.md              # このファイル
├── pyproject.toml         # プロジェクト設定
├── uv.lock               # 依存関係ロックファイル
└── src/                  # ソースコード
    └── main.py           # メインプログラム
```

## 必要条件

- Python 3.11以上
- uv (Pythonパッケージマネージャー)

## インストール

### 1. uvのインストール

```bash
# macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows (PowerShell)
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"

# pipxを使用
pipx install uv

# pipを使用
pip install uv
```

### 2. プロジェクトのセットアップ

```bash
# リポジトリをクローン
git clone <repository-url>
cd uv-ruff-project

# 依存関係をインストール
uv sync
```

## 使用方法

### プログラムの実行

```bash
# メインプログラムを実行
uv run python src/main.py

# または仮想環境を有効化してから実行
source .venv/bin/activate  # Linux/macOS
# または
.venv\Scripts\activate     # Windows
python src/main.py
```

### 開発コマンド

```bash
# 依存関係の追加
uv add package-name

# 開発用依存関係の追加
uv add --dev package-name

# 依存関係の削除
uv remove package-name

# 仮想環境の再作成
uv sync --reinstall

# プロジェクトの実行
uv run python src/main.py
```

### コード品質管理

```bash
# Ruffでリント実行
uv run ruff check .

# Ruffで自動修正
uv run ruff check --fix .

# Ruffでフォーマット
uv run ruff format .

# すべてのチェックを実行
uv run ruff check . && uv run ruff format .
```

## 開発

### 新しい依存関係の追加

本番依存関係を追加する場合：
```bash
uv add requests numpy pandas
```

開発用依存関係を追加する場合：
```bash
uv add --dev pytest black mypy
```

### 設定ファイル

- `pyproject.toml`: プロジェクトの設定、依存関係、ツール設定
- `uv.lock`: 依存関係のロックファイル（コミット推奨）
- `.gitignore`: Git無視パターン

## トラブルシューティング

### 仮想環境の問題

```bash
# 仮想環境をクリーンアップ
rm -rf .venv
uv sync
```

### 依存関係の問題

```bash
# ロックファイルを更新
uv lock --upgrade
uv sync
```

## ライセンス

[ライセンスを指定してください]

## 貢献

プルリクエストやIssueを歓迎します。