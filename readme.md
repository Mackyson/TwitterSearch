# Twitter検索ツール
## 開発環境
* Golang v1.14.4
* Elasticsearch v7.8.0
* Kibana v7.8.0

完璧に同じ環境じゃなくても全然動くと思いますが，困ったらバージョンを確認してください．

## 使い方
実行前にdocker-composeを入手してください．
```
$ sudo docker-compose up -d
$ cd ./SeachTweets && go build -o ../Search && cd ..
$ ./Search -query=from:@Twitter -count=20
```

これで@Twitterのツイートを20件取得できます．countは最大100までです．

取得したデータはlocalhost:5601にブラウザでアクセスして，左のバーにあるDiscoverのページで見ることが出来ます(Kibanaの起動は遅いので注意)．
## (DB以外を)改造する際の前提知識
* Twitter APIのKeyとSecretを取得できる
* ベアラートークンを使ってSearch APIを叩ける
* Twitter APIドキュメント(英語)を読める
* docker-compose.ymlに何が書いているかわかる

DBについては./SearchTweets/db/readme.mdを読んでください．
