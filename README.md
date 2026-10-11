# 編集ロック

Kenji のスマホ用の小さなアプリ。サイト（kekkon-roadmap）の「編集ロック」を見て、スライドで ON/OFF する。

- 記録の置き場所: 非公開リポ `kenji0618y/edit-locks` の `locks/<site>.json`（GitHub Contents API、sha で同時書き込みを検出）
- 鍵（GitHub の fine-grained token）は **このページには入っていません**。初回にスマホで入力し、その端末の localStorage にだけ保存します。
- AI 側は `/workspace/tools/edit-lock.mjs`（同じ記録を読み書き）。

- CSP（2026-10-12）: スクリプトはページ内の1つだけ（sha256）、通信先は api.github.com だけ。**`<script>` を直したら sha256 を計算し直して meta の CSP を更新すること**（しないとページが動かない）。
  `python3 -c "import re,hashlib,base64;s=open('index.html').read();print(base64.b64encode(hashlib.sha256(re.search(r'<script>(.*?)</script>',s,re.S).group(1).encode()).digest()).decode())"`
