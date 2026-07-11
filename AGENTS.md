# AGENTS.md

## Pull Request

- Pull Requestのタイトルと本文は日本語で記述する。
- タイトルは変更内容を簡潔に表す。
- 本文には、変更の目的、主な変更点、影響、確認方法を記載する。
- `.github/PULL_REQUEST_TEMPLATE.md` の構成に従う。
- Pull Requestは、明示的にDraft指定された場合を除き、レビュー可能な状態（Ready for review）で作成する。

## リポジトリの正本

- プロダクトの概要と利用方法は `README.md` を正とする。
- Pull Requestの記載項目は `.github/PULL_REQUEST_TEMPLATE.md` を正とする。
- 設計判断、仕様、運用手順は、口頭やチャットだけで完結させず、必要に応じてリポジトリ内のMarkdownとして管理する。
- `AGENTS.md` には運用上の入口と必須ルールのみを記載し、詳細な説明は関連ドキュメントへ分離する。

## 変更と検証

- 変更前に、関連する仕様・既存実装・設定を確認する。不明な仕様を推測で固定しない。
- Pull Request作成前に、変更に応じたテスト・lint・動作確認を実施する。
- 実施内容と結果、未実施の場合は理由と代替確認をPull Request本文の「確認方法」に記載する。
- 変更と無関係な修正は同じPull Requestに含めない。
