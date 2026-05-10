# 1-sand

GitHub ポートフォリオ向けの README テンプレートです。
単なる成果物の説明ではなく、「何を作ったか」「どう考えて解決したか」が伝わる構成にしています。

## プロジェクト概要

このプロジェクトは、課題整理から実装、検証までの流れを整理して示すためのサンプル README です。
実際のプロジェクト名や内容に合わせて、各セクションを差し替えて使ってください。

## 使用技術

- Backend: Python / Flask / Django など
- Frontend: JavaScript / HTML / CSS
- Database: SQLite / PostgreSQL など
- Tools: GitHub Actions / Markdown / Docker など

## 解決した技術的課題とプロセス

### 1. 非同期処理による表示の不整合

**問題**

API からのレスポンスを待たずに画面更新が走り、古いデータが表示される状態が発生しました。

**思考と解決策**

最初は待ち時間を固定する方法も検討しましたが、通信状況によって再現性が変わるため、本質的な解決にならないと判断しました。
そこで、処理の完了を明示的に待てるように `async/await` を導入し、データ取得後にのみ UI を更新する流れへ修正しました。

**確認コマンド**

```bash
pip freeze > requirements.txt
```

### 2. CORS エラー

**問題**

フロントエンドからバックエンドへリクエストした際、ブラウザの同一生成元ポリシーにより通信がブロックされました。

**思考と解決策**

エラーメッセージから原因が CORS であることを切り分け、バックエンド側に CORS 設定を追加しました。
必要なオリジンだけを許可するように調整し、安全性と開発体験の両立を図りました。

## セットアップ

### 1. リポジトリをクローン

```bash
git clone https://github.com/your-username/your-repository.git
cd your-repository
```

### 2. 環境構築

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### 3. 起動

```bash
python app.py
```

ブラウザで http://localhost:5000 を開いてください。

## ディレクトリ構成

```text
.
├── README.md
├── app.py
├── requirements.txt
└── static/
	├── css/
	└── js/
```

## スクリーンショット

実際の画面キャプチャを 1 枚入れると、完成度が伝わりやすくなります。

```md
![アプリ画面](./docs/screenshot.png)
```

## 作者

- 名前: あなたの名前
- GitHub: https://github.com/your-username
- X: https://x.com/your-handle

## 補足

README では、「何をしたか」だけでなく「なぜその方法を選んだか」を短く添えると、問題解決のプロセスが伝わりやすくなります。