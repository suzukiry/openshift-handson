# はじめに

Red Hat OpenShift Pipelinesは、Kubernetesリソースに基づくクラウドネイティブの継続的インテグレーションおよび継続的デリバリー（CI / CD）ソリューションです。

Tektonビルディングブロックを使用して、基盤となる実装の詳細を抽象化することにより、複数のプラットフォームにわたる展開を自動化します。

Tektonは、Kubernetesディストリビューション間で移植可能なCI / CDパイプラインを定義するためのいくつかの標準カスタムリソース定義（CRD）を導入しています。 

## ラボ概要

OpenShift Pipelines Operatorはすでにデプロイされているため、すぐに開始できます。

このラボでは、

1. 新しいプロジェクトを作成し、1つのパイプラインで "helloworld" という簡単なタスクをデプロイします
2. 2層の Golang のアプリケーションを構築およびデプロイするために必要なさまざまなリソースをデプロイします

3. ゴール
* 簡単なパイプラインのデプロイ
* ビルドパイプラインのデプロイ

## tkn コマンドなどのインストール (補足)
今回のLabでは tkn コマンドは使いませんが、利用イメージをご紹介します。

1. Taskの一覧を表示
```bash

tkn task list
```

> Taskが登録されていないことがわかります。

2. ClusterTaskの一覧を表示
```bash
tkn clustertask list
```

> ClusterTaskは、Tekton Catalogの一部がデフォルトで登録されていることがわかります。

3. その他の役立つコマンドとして、`kubens`をダウンロード・インストール
```bash
git clone https://github.com/ahmetb/kubectx.git
sudo install ./kubectx/kubens /usr/local/bin/
kubens -c
```

> namespaceの切り替えに便利です。
