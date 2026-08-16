# GitHub Copilot Loop Kit

このフォルダ内の`.github`ディレクトリを、対象リポジトリのルートへコピーしてください。

配置後は次の構成になります。

```text
<repository-root>/
└─ .github/
   ├─ copilot-instructions.md
   ├─ copilot-learnings.md
   ├─ instructions/
   │  └─ tests.instructions.md
   └─ prompts/
      ├─ analyze-session-history.prompt.md
      ├─ review-current-session.prompt.md
      ├─ weekly-instruction-review.prompt.md
      ├─ mine-session-logs.prompt.md
      └─ apply-approved-instructions.prompt.md
```

## 最初に行うこと

1. `.github`フォルダを対象リポジトリへコピーする。
2. GitHub Copilot Chatを対象リポジトリで開く。
3. `/analyze-session-history`を実行する。
4. 提示された分析とdiffを人間が確認する。
5. 採用する項目を指定して`/apply-approved-instructions`を実行する。

Copilot CLIまたはGitHub Copilotアプリを利用している場合は、最初に次も実行できます。

```text
/chronicle improve
```

## 日常運用

- 重要な作業の終了時：`/review-current-session`
- 週1回：`/weekly-instruction-review`
- 履歴が大量にある場合：`/mine-session-logs`
- 内容を確認して反映するとき：`/apply-approved-instructions`

## Prompt fileが表示されない場合

Prompt filesはVS Code、Visual Studio、JetBrains IDEで利用できます。VS Codeで必要な場合は、ワークスペース設定のJSONへ次を追加してください。

```json
{
  "chat.promptFiles": true
}
```

その後、Copilot Chatで`/`を入力し、prompt file名を選択します。

## 注意

- セッションログをリポジトリへコピーまたはコミットしないでください。
- `.github/copilot-learnings.md`は改善候補の置き場です。未検証の項目を確定ルールとして扱わないでください。
- `.github/copilot-instructions.md`には、複数セッションで確認され、リポジトリ全体に適用できるルールだけを残してください。
- 特定パスだけに必要な指示は`.github/instructions/*.instructions.md`へ分離してください。
- lint、formatter、テスト、CIで強制できる内容は、可能ならそちらへ移してください。

## 参考資料

- 動画：<https://www.youtube.com/watch?v=ifAt7nkaTww>
- Copilot CLI session data：<https://docs.github.com/en/copilot/how-tos/copilot-cli/use-copilot-cli/chronicle>
- Prompt files：<https://docs.github.com/en/copilot/tutorials/customization-library/prompt-files>
- Copilot customization cheat sheet：<https://docs.github.com/en/copilot/reference/customization-cheat-sheet>

