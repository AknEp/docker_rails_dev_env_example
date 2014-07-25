# Rails4.1 + Vagrant + Docker で良い感じに動かすサンプルコード

"【翻訳】DockerとVagrantによるRails開発環境 - Qiita" http://qiita.com/cieux1@github/items/b2294f8adddefb357a37?utm_content=buffer4754f&utm_medium=social&utm_source=facebook.com&utm_campaign=buffer

こちらで使用されているリポジトリで、動かなかった部分を少々修正しています。また、このREADMEドキュメントを追加しています。

元のサンプルには(何故か)Redisが入っていましたが、上手く動かなかったので本リポジトリでは削っています。


## 実行方法

まず、以下のものを導入します。

* VitrualBox (Vagrantがサポートしているものなら何でも良い気がします）
* Vagrant

次に、以下のコマンドを実行します。
他のプロセスが3000番ポートを既に占有していないか注意して下さい。

```
$ vagrant up
$ ./d cmd "bundle exec rake db:create db:migrate"
```

失敗した時は、 ```vagrant destroy``` で消し飛ばしましょう。 使い終わったら ```vagrant suspend``` / ```vagrant resume``` で一時停止と再開が出来ます。

Windowsでは、Vagrantfileのsync_folderを書き換える必要がありそうです。 :smb にするだけで動くのかどうか、未検証です。

### Rails 環境の動作確認

http://localhost:3000/cars

を見ると良いです。