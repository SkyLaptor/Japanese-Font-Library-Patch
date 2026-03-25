# 開発ガイドライン

## はじめに（必ずお読みください）

本プロジェクトへの貢献を検討いただきありがとうございます。 メンテナーの負担軽減とプロジェクトの品質維持のため、以下のルールを遵守してください。これらが守られていないプルリクエストは、内容を確認せずにクローズする場合があります。

* Issue優先: 大きな変更や機能追加を行う前に、必ずIssueで提案し合意を得てください。
* 最小PRs: 変更は可能な限り最小単位に分割してください。巨大な変更はレビュー対象外となります。
* 品質管理: ローカルでのビルドおよびテスト通過は必須条件です。

## 開発フロー

本リポジトリでは GitLab-Flow を採用しています。

1. mainブランチ: 全ての開発のベースです。
2. 作業ブランチ: `main` からブランチ( `feature/issue-番号` 等）を切って作業してください。
3. マージ: `main` へのマージは、レビュー承認およびCI通過後に行われます。
4. プレリリース: 仮公開は、`main` から `pre-production` ブランチへのマージによって実行されます。
5. リリース: 公開は、`pre-production` から `production` ブランチへのマージによって実行されます。

## 大まかな開発手順

1. リポジトリから `main` ブランチをクローン/チェックアウトする。
2. 開発ツール類、テスト環境をセットアップする。
3. コンテンツを修正し、テストを実行する。
4. `main` ブランチに対してプルリクエストを作成する。

## テスト環境

* 対象のModマネージャー: [Vortex](https://www.nexusmods.com/about/vortex), [ModOrganizer2](https://www.nexusmods.com/about/vortex) ※公式そのままの状態でカスタムを加えていないものであること。

## MOD追跡情報

### SkyUI

#### SkyUI v5.1 (2015.4.18)

<https://www.nexusmods.com/skyrim/mods/3863>

スカイリム用。

#### SkyUI v5.2 (2017.10.4)

<https://www.nexusmods.com/skyrimspecialedition/mods/12604>

スカイリムSE用。長らくこのバージョンだったため、これ用のパッチは残しておいた方が良いかもしれない。

#### SkyUI v6.4 (2026.3.25)

<https://www.nexusmods.com/skyrimspecialedition/mods/12604>

スカイリムSE用。

## Fomodについて

下記ドキュメントを参考にしてインストーラーを構成します。
<https://fomod-docs.readthedocs.io/en/latest/index.html>

## Fomodインストーラーのビルド

完成しリリースする際には、以下でビルドを行います。

1. `build_installer.cmd` を開いて `VERSION` を修正します。
2. `$ cmd /c .\build_installer.cmd` を実行します。
3. `build` ディレクトリにインストーラー( `Japanese-Font-Library-Patch_{バージョン番号}.7z` )が出来上がるので、GitHub 及び NexusMods にリリースします。
