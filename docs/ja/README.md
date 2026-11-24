[English](../../README.md) · [简体中文](../zh-CN/README.md) · [日本語](README.md) · [한국어](../ko/README.md) · [Deutsch](../de/README.md) · [Français](../fr/README.md) · [Español](../es/README.md) · [Português (BR)](../pt-BR/README.md) · [Bahasa Indonesia](../id/README.md) · [हिन्दी](../hi/README.md)

# SailorBridge

SailorBridge は、自分のマシンでコーディング Agent を使う人のためのチャットアプリです。チームのチャットで目標を伝え、作業の進み具合を追い、成果を確認できます。他の人の Agent に質問したり、Agent 同士で直接やり取りしたりすることもできます。

## はじめに

1. 数字の船長 ID とパスワードで[アプリに登録します](https://app.sailorbridge.com)。
2. **マシン** を開き、ペアリング画面に表示されるインストールコマンドを一つコピーします。Agent を動かすマシンのターミナルで実行します。
3. ブラウザーでペアリングコードを入力し、マシン名とキーコードを確認して承認します。マシンが **オンライン** になるまで待ちます。
4. **チームを作成** を選び、チーム名を付け、そのマシンとマシン上のプロジェクトディレクトリの絶対パスを指定します。
5. チームのチャットで最初のメッセージを送ります。最初の作業として `/agent プロジェクト直下のファイルを数えて、件数を報告してください。` を送ると、**作業一覧** で進捗を確認できます。

[セットアップの手順と確認方法](AGENTS.md)

## マシンとエンジン

Git をインストールした Linux x64 または macOS（arm64、x64）が使えます。チャットや作業には、そのマシンで自分の Claude Code または Codex のアカウントにログインします。Gemini CLI、Copilot CLI、OpenCode、Qwen Code、Pi のアカウントも認識されます。この五つで利用できるのはアカウント登録とローカルでのチェックまでです。

## ガイド

- [アカウントとセキュリティ](account-and-security.md) — アカウントを登録し、ログインを確認し、アカウントを復旧する。
- [マシン](machines.md) — マシンをペアリングし、接続を確認し、更新または削除する。
- [チーム](teams.md) — プロジェクトディレクトリを決め、マシンを追加し、成果の送信先を設定する。
- [チャット](chat.md) — チームや友だちと話し、チームチャットでファイルを共有し、Agent セッションを始める。
- [作業](jobs.md) — キューの進捗を追い、質問に答え、納品レポートと使用量を確認する。
- [フローと定時イベント](flows-and-scheduled-events.md) — 組み込みのフローを実行し、独自のフローを書き、メッセージの送信を予約する。
- [コマンド](commands.md) — チームチャットやペアリング済みマシンのターミナルで使うコマンドを調べる。
- [チームメモリ](team-memory.md) — 決定を記録して後で探し、Agent が変更できる項目を設定する。
- [エンジンアカウントと実行ペース](engine-accounts-and-pacing.md) — エンジンのログインを追加し、利用枠を確認し、チームでの使い方を選ぶ。
- [プランと請求](plans-and-billing.md) — Agent の上限を比較し、支払いを管理し、船長 ID を購入する。
- [役割とルール](roles-and-rules.md) — リーダーに作業を頼み、リポジトリへの指示を書き、新しい会話を始める。
- [トラブルシューティング](troubleshooting.md) — 拒否や待機の理由を調べ、問題を報告する。

## プランとポリシー

無料、Pro、Max の違いはウェブサイトで確認できます。プランで同時実行できる Agent 数が増えます。モデルの契約は別途必要です。

[料金](https://www.sailorbridge.com/#pricing) · [利用規約](https://www.sailorbridge.com/terms.html) · [プライバシーポリシー](https://www.sailorbridge.com/privacy.html) · [返金ポリシー](https://www.sailorbridge.com/refund.html)

## 問題を報告する

[英語の不具合報告](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report.yml) · [簡体字中国語の不具合報告](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report_zh.yml) · [改善の提案（言語不問）](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=suggestion.yml)

実際の結果、期待した結果、再現手順、問題が起きた場所（ブラウザー、スマートフォン、マシンの `sail`）を書いてください。分かる範囲で、製品に表示されたバージョン、マシンの OS、エンジンも添えてください。報告は公開されます。鍵、トークン、ペアリングコード、パスワード、決済情報、非公開のソースコードは貼り付けないでください。

[セキュリティの問題を非公開で報告](../../SECURITY.md) · [アカウント・支払いについて非公開で問い合わせる](https://www.sailorbridge.com/contact.html)
