# k8s-misskey-ni_rilana

こちらの記事[「おうちKubernetesにmisskeyをデプロイする」](https://qiita.com/commojun/items/b9cb1ac7fb1b6c80d70a)を元に、Kubernetes+Rook/Ceph+CloudNativePGでMisskeyを構築する為のコンフィグリポジトリとなります。
元のデータとしてこちらの記事で使用されているリポジトリをForkして更新しています。
元データを閲覧したい方はFork元を確認してください。


## ファイル内容

```terminal
$ tree
.
├── README.md
├── namespace.yml
├── nirila
│   └── config
│       └── config-misskey-default.yaml
├── redis.yml
├── stateful-web.yaml
└── web-local.yaml
```

- README.md このファイル
- namespace.yaml ネームスペースを作成するためのファイル
- nirila/config/config-misskey-default.yaml misskey用ConfigMap
- redis.yml redis用yaml
- stateful-web.yaml misskey用yaml
- web-local.yaml ローカルテスト用yaml
  - もし連合させたくない場合等は適時`nirila/config.config-misskey-default.yaml`を編集してください

## 構築方法

以下の記事を参照してください。

[MisskeyをDockerからおうちKubernetesに移行する](https://qiita.com/arila/items/3c453b7e802639eebdea#misskey%E6%9C%AC%E4%BD%93)

もしNamespaceでエラーが発生した際は

```termial
$ kubectl apply -f namespace.yaml
```

を実行してNamespaceを作成してください。
