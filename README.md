# Agent Island Downloads

Claude Code、Codex、AGYの状態と承認待ちを、画面上部の小さなIslandへ集約するアプリです。

## リリース区分

- macOS `0.1.19`: 正式版
- Windows `0.1.19-beta.1`: 未署名プレリリース

Windows betaはWindows 11 x64／ARM64向けです。初回はCPUに合う`Setup.exe`を使用してください。
Portable版はインストールせず確認する場合に使用できます。

## Windowsへのインストール

1. Release assetsから`win-x64`または`win-arm64`の`Setup.exe`をダウンロードします。
2. 同じReleaseの`SHA256SUMS-win-x64.txt`または`SHA256SUMS-win-arm64.txt`と一致することを確認します。
3. SmartScreenが表示された場合は、配布元とSHA-256を確認してから「詳細情報」→「実行」を選びます。
4. 通知領域のAgent Islandアイコンを開き、設定から各CLIを接続します。
5. Codexは新しいセッションで`/hooks`を開き、Agent IslandのHookを信頼します。

```powershell
Get-FileHash .\ダウンロードしたファイル.exe -Algorithm SHA256
```

ハッシュが一致しないファイル、別サイトから取得したファイル、内容を確認できない警告は実行しないでください。

## Windows betaの既知制約

- Authenticode未署名のため、SmartScreenに「不明な発行元」と表示される場合があります。
- 異なる表示倍率の複数モニター構成は未検証です。単一モニターの100／125／150／200%を対象とします。
- CLIへのログインとCodex Hookの信頼操作は利用者本人が行う必要があります。
- 管理者として起動したCLIと通常権限のAgent Islandは接続できない場合があります。

Windows betaは公開GitHub Releasesを使って更新を確認します。正式版への昇格前に
Authenticode署名、Defender、混在DPIの複数モニターを含む全実機検証を完了します。

不具合報告はこのRepositoryのIssuesへ、OS、CPU、表示倍率、CLI名、再現手順を添えてください。
認証トークン、プロンプト本文、生Hook JSONは投稿しないでください。
