# aws-challenge-1
## aws-challengeとは
「aws-challenge」とは、 **AWS CloudFormation** や **Serverless Framework** を用いて構築されたAWS環境の不具合を見つけ解決しながらAWSに慣れ親しんでもらうことを目的とした学習課題です。

## イントロ 
EC2に作成したサイトがなぜか表示されない。

サイトに表示されるメンテナンス画面（503 Service Unavailable）では、ピンクの猫が忙しそうにキーボードをたたいている。

ネットワークの設定が悪いのか？

ロードバランサーの不具合か？

それとも

EC2の設定が原因なのか？

今回の課題は、「EC2のサイトが表示されない謎を解き明かせ」

挑戦者求！

## 今回作成される環境
![aws-challenge-1-environment](https://user-images.githubusercontent.com/11880332/62437051-91b69300-b77c-11e9-8680-6ba114435107.png)

* Amazon VPC
* Application Load Balancer
* Amazon EC2

### 確認事項
* EC2を作成しているため、AWS CloudFormationでcompleteになっても1分ほど環境が整わない時間がありますので、ゆっくりと挑戦してみてください。

## 環境
環境構築に **AWS CloudFormation** を利用します。

## 環境構築方法
AWS CloudFormationでスタック作成をします。

テンプレートのファイルのアップロードからaws-challenge1.yamlをアップロードします。

![スタック作成_censored](https://user-images.githubusercontent.com/11880332/62437901-1a82fe00-b780-11e9-80c7-772f8800138a.jpg)

スタックの名前と必要に応じてパラメータを調整してください。

![スタック2](https://user-images.githubusercontent.com/11880332/62437924-266ec000-b780-11e9-89fe-3aac6985c7e4.png)

### パラメータ

| パラメータ | デフォルト値 |説明|
----|----|---- 
| EC2InstanceAMI | ami-0c3fd0f5d33134a76 |デフォルトは Amazon Linux2のamiです。
| Stage | dev |アカウントで複数立ち上げる場合には、ユニークになるようにしてください
| VPCCIDR | 22.0.0.0 | アカウントで複数立ち上げる場合には、かぶらないようにしてください。

そのあとの画面は、何も設定しなくていいです。

![スタック3](https://user-images.githubusercontent.com/11880332/62437940-2d95ce00-b780-11e9-9d41-bf0667f9342c.png)

最後にIAMロールを作成するため、チェックボックスにチェックをして、スタックの作成をしてください。


## 課題確認方法

AWS CloudFormationでデプロイが完了すると出力タブにURLが払い出されます。
まずは、このURLを確認してください。

![スタック4_censored](https://user-images.githubusercontent.com/11880332/62438165-2a4f1200-b781-11e9-8e49-a050a9b3575c.jpg)

すると、なんということでしょう！

503 service unavailableページが表示されます。

ここからが課題のスタートです。

構築された環境の不具合を修正することにより、正常な画面が表示されます。

aws-challenge1.yamlを修正してもいいですし、AWSコンソールに入って調べてもかまいません。

解き方は自由です。

それでは、Let's enjoy!

## 注意事項

課題によっては、そのまま放置するとお金のかかるものもあります。きちんと環境は撤去するようにしてください。
