# cakephp3-centos-ansible


最小構成でインストールしたCentOSにCakephpを自動インストールするためのAnsibleプレイブックです。

コマンド5個実行するだけで、あとはしばらく放置すればインストールが完了します。


## 概要



## システム構成

* CentOS 7.3
* Apache
* php
* composer
* PostgreSQL
* CakePHP3


## CakePHP3のインストール手順

インストール直後の CentOS 7.3 に root でログインし以下の操作を行ってください。


### Ansibleとgitのインストール

```
yum update -y
yum install -y epel-release
yum install -y ansible
```

### playbookのダウンロード

```
# git clone https://github.com/kuki444/cakephp3-centos-ansible.git
# playbookをセット
cd /usr/local/src/cakephp3-centos-ansible
```

### PostgreSQLに設定するパスワードの変更

ダウンロードしたプレイブック内のファイル `group_vars/cakephp-servers` をエディタで開き、 `db_passwd_redmine` を適当な内容に変更してください。これはPostgreSQLのRedmine用ユーザー redmine に設定されるパスワードです。

### playbook実行

下記コマンドを実行してください。CakePHPの自動インストールが開始されます。

```
cd redmine-centos-ansible
ansible-playbook -i hosts site.yml
```

10〜20分ほどでインストールが完了します。webブラウザで `http://サーバIPアドレス/cakephp` にアクセスしてください。Cakeの画面が表示されるはずです。


## ライセンス

MIT License


## 作者

[kuki]
