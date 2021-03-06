## 楽しいこと
- 自分の成果が一目でわかる
- コミットしたかひと目でわかるので、コミットチェインを毎日つなげることで達成感が得られる

## GitLab でバージョン管理する目的
- いちいち「ファイル名_20171130.txt」のように管理しなくても変更履歴がわかる
- ブランチ(枝)を切ることで複数のバージョンを同時に管理することができる
- 差分が一発でわかる
- FTP環境にUPしないファイルも複数人で共有＋編集できるようにしたい

## ブランチの運用方針
__master__
常にリリース可能な状態（本番環境で動作しているコード)
タグをリモートリポジトリにプッシュ

__develop(master から派生)__
開発中の状態でステージング環境に上がっている

__release(develop から派生)__
リリース準備なので新機能の追加やバグ修正は行わない
作業はバージョンコードの変更など
master に marge しその後タグを付ける

__feature(develop から派生)__
新機能やバグ追加ごとのブランチ(feature/◯◯, feature/xxなど)

__hotfix(master から派生)__
リリースされた製品に致命的なバグ(クラッシュなど)があった場合に緊急対応するブランチ(hotfix/バージョン番号/xx)
