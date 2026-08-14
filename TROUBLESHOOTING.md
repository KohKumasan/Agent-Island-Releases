# Windows Troubleshooting

## SmartScreenが表示される

`0.1.19-beta.1`は未署名です。ReleaseのCPU別`SHA256SUMS-*.txt`とダウンロードファイルのSHA-256、
配布元Repositoryを確認してください。一致しない場合は実行しないでください。

## CLIが見つからない

Windows Terminalを開き直し、次を確認します。PowerShellの実行ポリシーで`.ps1`が止まる場合は
npm製CLIの`.cmd`を使用します。

```powershell
claude.cmd --version
codex.cmd --version
agy --version
```

## 接続したのに通知が来ない

- 接続後にCLIを再起動し、実際の依頼を1件送信します。
- Codexは新しいセッションの`/hooks`でAgent IslandのHookを信頼します。
- Agent IslandとCLIを同じ通常権限で起動します。

## 診断情報

- 設定: `%LOCALAPPDATA%\Agent Island\settings.json`
- 履歴: `%LOCALAPPDATA%\Agent Island\data\history.db`
- Hook: `%LOCALAPPDATA%\Agent Island\bin\agent-island-hook.exe`

認証トークン、プロンプト本文、生Hook JSONはIssueへ添付しないでください。
