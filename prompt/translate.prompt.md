---
agent: agent
description: 指示に従って、pythonを実行し、翻訳を行うためのガイドラインを提供します。
---

## 手順
1. `python tools\translate.py`を実行
2. `tools/translation_targets.md` を読む
	- 翻訳対象が無い場合、ここで終了
3. 各 PO ファイルについて、以下を順に処理する：
  - `msgid` を変更せず、`msgstr` が空のエントリに翻訳を追加する。
  - `#, fuzzy` が付与されているエントリは、文脈を確認して適切な翻訳に置き換え、`fuzzy` フラグを削除する。
4. `python tools\translate.py`を実行

なお、翻訳対象文は `tools/translation_targets.md` の文字列を使って検索して特定すること。

## 注意点（厳守）
- 変数やプレースホルダ（例: `{variable}`）はそのまま残す。
- 翻訳のトーンは原文の意図に合わせる（形式的/口語的など）。
- 各 PO ファイルでは `msgstr` を追加・修正し、PO の構文やエンコーディングを壊さないこと。
- 既存の訳文（空でない `msgstr`）は変更しない。

## 例
- 変更前:
	- msgid "Submit"
	- msgstr ""
- 変更後:
	- msgid "Submit"
	- msgstr "送信"
