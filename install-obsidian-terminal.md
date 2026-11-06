# Obsidianのターミナルで、Claude Code と Codex を動かす手順

Obsidianの中に黒い画面（ターミナル）を足して、そこから Claude Code と Codex を動かせるようにします。  
もう入っている物は飛ばしてください。Codexを使わない人は、手順3は要りません。

## 手順1　Obsidianにターミナルを足す（無料）

1. Obsidianの左下の歯車を押し、「コミュニティプラグイン」を開く
2. 「コミュニティプラグインを有効化」を押す
3. 「閲覧」を押し、`Terminal` で検索する
4. 開発者が **polyipseity** の「Terminal」を選び、「インストール」→「有効化」を押す（英語の説明ページが開いたら、閉じて大丈夫です）
5. Macは `Command + Shift + H`、Windowsは `Ctrl + Shift + H` を押す

画面の下に黒い画面が開き、今開いている保管庫の名前が見えれば完了です。

> 開かない時：Macでは裏で Python 3.9 以上を使います。Macの「ターミナル」アプリで `python3 --version` と打ち、入っていないと出たら `xcode-select --install` で入れて、Obsidianを開き直してください。キーが効かない時は、左のバーの「Open terminal」を押して「統合」と書かれた項目を選びます。

## 手順2　Claude Code を入れる

Claudeの有料プランが要ります。手順1で開いた黒い画面に貼って、Enterを押します。

**Mac**

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows**（スタートメニューから PowerShell を開いて貼る）

```powershell
irm https://claude.ai/install.ps1 | iex
```

途中の経過は表示されません。終わるまで待ってから、黒い画面を開き直して（タブを閉じて、もう一度キーを押す）、次を打ちます。

```bash
claude --version
```

番号が出たら入っています。続けて `claude` と打ち、ブラウザの案内に沿ってログインします。

## 手順3　Codex を入れる

ChatGPTのアカウントでログインします。使える範囲はプランで変わるので、公式の案内を確認してください。

**Mac**

```bash
curl -fsSL https://chatgpt.com/codex/install.sh | sh
```

**Windows**（PowerShell に貼る）

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://chatgpt.com/codex/install.ps1 | iex"
```

終わったら黒い画面を開き直して `codex` と打ち、「Sign in with ChatGPT」を選びます。

## 手順4　箱で動かす

1. Obsidianで `second-brain` を開く
2. `Command + Shift + H`（Windowsは `Ctrl + Shift + H`）で黒い画面を開く
3. `claude` と打つ。Codexなら `codex` と打つ
4. 最初に確認が出たら、矢印キーで Yes を選ぶ（Claude Codeは「Yes, I trust this folder」）
5. 次の文を打つ

```text
昨日の続き、何だっけ
```

見本の案件カードを読んで「次の一手」から答えたら、つながっています。  
Codexは `CLAUDE.md` を読まないので、入口の `AGENTS.md` を置いてあります。自分で作った箱で使う時も、`AGENTS.md` に「最初に `CLAUDE.md` を読む」と1行書いてください。

## うまくいかない時

- `command not found` と出る：黒い画面を開き直してください。それでも出る時は、公式の案内を見てください
- キーを押しても別の動きをする：別のプラグインとキーが重なっています。設定の「ホットキー」で変えられます
- 黒い画面を使いたくない：Claudeアプリの「Code」で `second-brain` を選べば、同じことができます

## 公式の案内

- Claude Code：https://code.claude.com/docs/en/setup
- Codex：https://developers.openai.com/codex/cli
- Terminalプラグイン：https://github.com/polyipseity/obsidian-terminal

確認した環境：2026年11月6日、Mac、Terminal 3.29.0。ターミナルの中で Claude Code と Codex が起動すること、`昨日の続き、何だっけ` にカードから答えることまで動かしました。インストールのコマンドは公式の案内のとおりです。Windowsの手順は公式の案内に沿って書いたもので、こちらでは動かしていません。
