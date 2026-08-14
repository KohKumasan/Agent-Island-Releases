# Privacy

Agent Islandはテレメトリ、広告、利用状況分析を送信しません。

Windows版がネットワークへ接続するのは、公開GitHub Releasesから更新情報と更新ファイルを
取得するときだけです。Claude Code、Codex、AGYの認証情報を読み取ったり保存したりしません。

ローカルには次の情報を保存します。

- `%LOCALAPPDATA%\Agent Island\settings.json`: 起動、ホットキー、更新確認などの設定
- `%LOCALAPPDATA%\Agent Island\data\history.db`: 秘密値を除いた状態履歴（7日、最大1,000件）
- `%LOCALAPPDATA%\Agent Island\bin\agent-island-hook.exe`: CLI連携用ヘルパー

履歴には認証トークン、プロンプト本文、生Hook JSON、承認対象のコマンド全文を保存しません。
設定画面の「履歴を削除」から履歴を消去できます。

CLI接続時は既存設定を保持したままAgent IslandのHook項目だけを追加し、初回変更前の設定を
`*.agent-island.backup`へ保存します。接続解除ではAgent Islandの項目だけを削除します。
