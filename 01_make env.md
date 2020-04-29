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

## GNS3とVirtualBoxのインストール

```console
❯ brew cask install gns3

# 下記の文字が出力されれば、無事インストール完了
🍺  gns3 was successfully installed!
```

```console
❯ brew cask install virtualbox

# 下記の文字が出力されれば、無事インストール完了
🍺  virtualbox was successfully installed!
```

## 仮想環境のインストール

下記サイトからGNS3VMをダウンロードし、ファイルを解凍する。
https://github.com/GNS3/gns3-gui/releases

//画像を差込//

VirtualBoxを起動し、先に解凍したファイルから**ovfファイル**を選択する。

//画像を差込//
//画像を差込//

## イメージのダウンロード
