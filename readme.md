# cloud9にてdocker/sailを利用したlaravel環境設定

## cloud9で環境設定

```markdown
Name： 自由
Description： 自由
Environment type：New EC2 instance
Instance type： Additional instance types t2.small
Connection: Secure Shell (SSH)
その他は変更なし
```

* dockerはすでに入っているので確認

`$ docker -v`

* docker composeの利用

docker composeが入っていないので、入れる。

[公式を参照](https://docs.docker.com/compose/install/other/)

もしくは、[ここ](https://www.seeds-std.co.jp/blog/creators/2022-12-02-122250/)が参考になる

入れられたら、

`$ docker compose version`

で確認

## laravelを入れる

※基本は、laravel[公式](https://laravel.com/docs/9.x#getting-started-on-linux)を参照

* `sail`を導入

**↓↓ example-appのは任意のプロダクト名(ディレクトリ名)にする。**

`$ curl -s https://laravel.build/example-app | bash`

## より良い環境設定

* `.env`に追記

以下`APP_XXXX`付近に追加

```log
APP_PORT=8080
```

* PATHの設定

`$ vi ~/.bash_profile`

以下 追記

```bash
alias sail="./vendor/bin/sail"
```

`$ source ~/.bash_profile`

* 実行

*※下のexample-appはご自身で作成したプロジェクト名に変えてください。※*

`$ cd example-app`

`$ sail up -d`

※初回起動時はちょっと時間かかる

* 確認

cloud9の`Preview`から`Preview running application`で画面を確認
