# Note Writer

note向け記事とThreadsスレッドをAIで生成するためのスキル集と運用メモを管理するリポジトリです。

## ファイル構成
- `SKILL.md`: Claudeに読み込ませるメインスキル。note記事作成からThreads展開までの4フェーズワークフローを定義
- `docs/account/note_account_design.md`: アカウント「毎日ガジェット便り」のブランド方針やコンテンツ運用メモ
- `sample_SKILL.md`: 既存の参考スキル（書き方のみ参考用）

## 使い方
1. `docs/account/note_account_design.md`でアカウントの方向性やトーンを確認
2. ご自身のテーマと商品情報を整理し、`SKILL.md`のPhase 0テンプレに沿ってClaudeへ入力
3. 出力されたnote記事ドラフトを加筆修正しつつ公開
4. 同時に提供されるThreadsテンプレをコピペしてスレッド投稿

## 補足
- noteとThreads以外（XやInstagramなど）に展開したい場合は、`SKILL.md`に追加ルールを追記して拡張してください。
