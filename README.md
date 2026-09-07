# claude-plugins

私の自作 Claude Code プラグインの配布元（マーケットプレイス）です。プラグインの本体はそれぞれのリポジトリにあり、ここには `marketplace.json` だけを置いています。

| プラグイン | 中身 | リポジトリ |
|---|---|---|
| discord-bot | Claude Code の Discord チャンネルセッションを Discord 側から管理する | https://github.com/ryuki-imachi/claude-code-discord-bot |
| blog-skills | ブログ執筆スキル一式（投稿前レビュー、Qiita 投稿準備、投稿後の後片付け、drawio 図の書き出し） | https://github.com/ryuki-imachi/blog-skills |

## 使い方

マーケットプレイスを一度登録すると、`<プラグイン名>@ryuki-plugins` でインストールできます。

```
claude plugin marketplace add ryuki-imachi/claude-plugins
claude plugin install blog-skills@ryuki-plugins
claude plugin install discord-bot@ryuki-plugins --scope project
```

各プラグインの導入手順と設定は、それぞれのリポジトリの README を見てください。

## 開発中のプラグインを試す

このリポジトリを clone し、`marketplace.json` の該当プラグインの `source` を手元のパス（このファイルからの相対パス、例 `../blog-skills`）に書き換えてから、clone したディレクトリを登録します。

```
claude plugin marketplace add ~/path/to/claude-plugins
```

同じ名前（ryuki-plugins）の登録は1つしか持てないので、GitHub 版に戻すときは `claude plugin marketplace add ryuki-imachi/claude-plugins` を再実行して置き換えます。

## ライセンス

MIT
