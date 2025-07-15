# 個人設定

## コード作成時の基本方針
- コードとドキュメントを必ずセットで作成
- 学習目的のため、実装理由や設計思想も説明
- 日本語コメントを豊富に含める
- 段階的な理解ができるよう構成

## コードスタイル
- 関数・クラスには必ずdocstringを日本語で記述
- 複雑なロジックには行コメントで説明
- 変数名は長くても意味が分かりやすいものを使用

## タスク完了時の対応
- すべてのタスクが完了したら、完了通知を明確に表示する
- 実装した機能の動作確認方法も併せて案内する

### 通知方法
#### Windows通知ダイアログ
PowerShellのMessageBoxを使用してネイティブ通知を表示：
```bash
powershell -c "Add-Type -AssemblyName System.Windows.Forms; [System.Windows.Forms.MessageBox]::Show('タスクが完了しました！\n\n実施内容：[具体的な作業内容]\n動作確認方法：[確認手順]', 'Claude Code - タスク完了通知', 'OK', 'Information')"
```

#### 設定要件
settings.local.jsonでの許可設定が必要：
```json
"allow": [
  "// Windows通知用PowerShellコマンドのみ許可",
  "Bash(powershell -c \"Add-Type -AssemblyName System.Windows.Forms; [System.Windows.Forms.MessageBox]::Show*)"
]
```