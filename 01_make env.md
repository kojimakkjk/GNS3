# MacでGNS3を導入

## はじめに

実機ではなかなか構築が難しい、ネットワーク機器の環境を、PC上で再現する。備忘録としてMacにGNS3のインストールする方法を記載する。

構築の流れは以下の通り

1. 構築前の環境確認
2. GNS3のインストール
3. VIRLからイメージのダウンロード

## 構築前の環境確認

環境は下記の通り

```console
❯ sw_vers
ProductName:	Mac OS X
ProductVersion:	10.15.4
BuildVersion:	19E287
```

``homebrew``でパッケージ管理を行うため事前に、インストールを行う。

## GNS3とvmware-fusionのインストール

```console
❯ brew cask install gns3

# 下記の文字が出力されれば、無事インストール完了
🍺  gns3 was successfully installed!
```

```console
❯ brew cask install vmware-fusion

# 下記の文字が出力されれば、無事インストール完了
🍺  vmware-fusion was successfully installed!
```

## 仮想環境のインストール

下記サイトからGNS3VMをダウンロードし、ファイルを解凍する。
https://github.com/GNS3/gns3-gui/releases

//01 VMware 画像を差込//

VMwareを起動し、先に解凍したファイルから**ovfファイル**を選択する。

//02,03,04,05//

VMのメモリ等を設定して、完了。PCにメモリの余裕があれば、増やし、余裕がなければ、初期設定で問題なし。また、**KVM**の設定が**True**であることを確認する。

//05-2//

## GNS3の起動

アプリケーションから**GNS3**を起動し、**Preferences**を開く。ショットカットコマンド``comand + ,``

//06//

設定で**Enable the GNS3 VM**にチェックマークを入れ、**VMware fution**を選択する。

## イメージのダウンロード

Ciscoの公式サイトで**VIRL(Cisco Virtual Internet Routing Lab)を購入し、GNS3へ登録

http://virl.cisco.com/index.php

その他の入手方法は下記を参照

https://docs.gns3.com/1vJwh4_whwtfjb8pQ8vKekcWrA1galIqA1eHgeClOsPY/index.html

## イメージの登録

**GNS3**を起動し、**Preferences**を開く。ショットカットコマンド``comand + ,``

**Qemu VM templates**を選択し必要な情報を入力しつつ、進める。

//09,10,11//

|イメージ名|RAM|
|---|---|
|IOSv|512MB|
|IOSvL2|768MB|
|ASAv|2,048MB|
|XRv|3,072MB|
|XRv 9000|16,384MB|

**Servers Summary**がVMとlocalが共に緑色に点灯していることを確認する。

//12//

## その他

VirtualBox と VMwareはどちらが良いのか？
https://docs.gns3.com/1wdfvS-OlFfOf7HWZoSXMbG58C4pMSy7vKJFiKKVResc/index.html

## 参考にしたサイト

GNS3公式「GNS3 installation on MacOS X」
https://docs.gns3.com/1MlG-VjkfQVEDVwGMxE3sJ15eU2KTDsktnZZH8HSR-IQ/index.html

YOUTUBE「GNS3 w/VMWare Fusion and switches set up」
https://www.youtube.com/watch?v=oxNmGdEAL1Y