# claude-plugins

私の自作 Claude Code プラグインの配布元（マーケットプレイス）です。プラグインの本体はそれぞれのリポジトリにあり、ここには `marketplace.json` だけを置いています。

| プラグイン | 中身 | リポジトリ |
|---|---|---|
| discord-bot | Claude Code の Discord チャンネルセッションを Discord 側から管理する | https://github.com/umitsu-tech/claude-code-discord-bot |
| blog-skills | ブログ執筆スキル一式（投稿前レビュー、Qiita 投稿準備、投稿後の後片付け、drawio 図の書き出し） | https://github.com/umitsu-tech/blog-skills |

## 使い方

マーケットプレイスを一度登録すると、`<プラグイン名>@ryuki-plugins` でインストールできます。

```
claude plugin marketplace add umitsu-tech/claude-plugins
claude plugin install blog-skills@ryuki-plugins
claude plugin install discord-bot@ryuki-plugins --scope project
```

各プラグインの導入手順と設定は、それぞれのリポジトリの README を見てください。

## 開発中のプラグインを試す

`marketplace.json` の `source` にはマーケットプレイスの直下より上（`..` を含むパス）を指定できないので、手元のリポジトリを指す登録用ディレクトリを別に作り、その中にシンボリックリンクを置きます。

```
mkdir -p ~/claude-plugins-local/.claude-plugin
cd ~/claude-plugins-local
ln -s ../blog-skills blog-skills
ln -s ../claude-code-discord-bot discord-bot
```

`.claude-plugin/marketplace.json` はこのリポジトリのものをコピーし、`source` を `"./blog-skills"` のようにリンク名へ書き換えます。そのディレクトリを登録すると、同じ名前（ryuki-plugins）の登録が置き換わり、`claude plugin install <名前>@ryuki-plugins` で手元のリポジトリから入ります。

```
claude plugin marketplace add ~/claude-plugins-local
```

GitHub 版に戻すときは `claude plugin marketplace add umitsu-tech/claude-plugins` を再実行します。

## ライセンス

MIT
