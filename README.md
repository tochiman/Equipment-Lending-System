# Equipment-Lending-System


# 【基本設計書】知念研備品貸し出しシステム

## 担当者
|分野|担当者|
|---|---|
|Frontend | TMm20138 |
|Backend | tochiman |
|Infra | TMm20138＆tochiman |

## 使用技術
- Nextjs(Frontend)
    - Material UI(UI library)
    - NextAuth.js(Login)
- Golang(Backend)
    - Gin
    - go-sql-driver
- Docker(Development)
- Kubernetes(deployment)
    - kubeadm
    - containerd
    - runc
    - metallb
    - cilium(CNI)

## Githubのルール
- [Repositry:Equipment-Lending-System](https://github.com/tochiman/Equipment-Lending-System.git)をリモートリポジトリとする
- 開発中は以下のブランチ名の中で開発する
    - TMm20138が`miyabe-develop`
    - tochimanが`tochiman-develop`

- 機能が一つ完成したら、PullRequestを飛ばす。この時、レビュワーはPullRequestを送っていない人が行う。確認後MainブランチにMergeする。