
# sakuracloud-maintenance-checker
さくらクラウドのメンテナンス情報の有無をチェックする。  

## 機能

 * 引数にIPを利用する。
 * さくらのクラウドのAPIを利用して、インスタンスのメンテナンス情報を参照する。

 ## 動作用件

 * Python3
 * Ubuntu

 ## 設定

 スクリプト内のapi情報を書き換える。  
 APIキーのアクセスレベルはリソース閲覧以上が必要。

  |変数|設定値|
  |---|---|
  |apikey|さくらのクラウドのアクセストークン|
  |apisecret|さくらのクラウドのアクセストークンシークレット|
  |url|さくらのクラウドのAPI URL|


 ## CLI

 ```
 ./check.py InstanceIP
 ```
 * メンテナンス情報がある場合は対象URLが出る。
 * メンテナンス情報がない場合は0を返す。
 * エラーの場合は内容に応じたメッセージが出る。
    * "API key not exist." API情報が空のときに表示される。
    * "API server error Code" APIserverから200以外のステータスが返ったときに表示される。
    * "引数が足りません。" 引数をつけずに実行したときに表示される。
    * "ip address not found" 指定したIPアドレスのサーバが存在しない時に返すメッセージ。

## 参考
https://developer.sakura.ad.jp/cloud/api/1.1/