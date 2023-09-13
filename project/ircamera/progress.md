# progress
- [progress](#progress)
  - [赤外線投光器の作成](#赤外線投光器の作成)
  - [piのセットアップ](#piのセットアップ)
  - [動画撮影用スクリプトの作成](#動画撮影用スクリプトの作成)
  - [遠隔で確認する](#遠隔で確認する)
  - [実践](#実践)
  - [参考](#参考)

## 赤外線投光器の作成

## piのセットアップ
### カメラのコネクションをenableに
`$ sudo raspi-config`内のInterfaceng optionからカメラを選択し、enableへ

`$ vcgencmd get_camera`でカメラの状況を確認

今回使用するのはカメラモジュールV3のため、OSが最新のBullseyenになっているか確認する。
`lsb_release -a`

## 動画撮影用スクリプトの作成

## 遠隔で確認する

## 実践

## 参考
