# 編集ロック

Kenji のスマホ用の小さなアプリ。サイト（kekkon-roadmap）の「編集ロック」を見て、スライドで ON/OFF する。

- 記録の置き場所: 非公開リポ `kenji0618y/edit-locks` の `locks/<site>.json`（GitHub Contents API、sha で同時書き込みを検出）
- 鍵（GitHub の fine-grained token）は **このページには入っていません**。初回にスマホで入力し、その端末の localStorage にだけ保存します。
- AI 側は `/workspace/tools/edit-lock.mjs`（同じ記録を読み書き）。
