て、下部の Import ボタンを押して全てをインポートします
6. インポートが完了し、左のメニューペインの中、▼My drive の下に Oracle Compute Cloud Service というツリーが現れたことを確認します

## 使い方
1. まず左のメニュー上部の CONTEXT タブを選択します
2. GLOBAL というものの中に、あなたの持つ Compute Cloud の環境に合わせた変数を定義します
    - **api_endpoint**
        - Compute Cloud の APIエンドポイントです(例 : api-z26.compute.us2.oraclecloud.com)  
          Compute Cloud の詳細画面に表示される REST API エンドポイントの値をそのまま入力してください
    - **identity_domain**
        - アイデンティティ・ドメインID (もし表示名を変えている場合も元のIDを指定)
    - **username**
        - アクセスに使用するユーザー名
    - **password**
        - アクセスに使用するパスワード
    - **test_case_name**
        - テストに使用する際の任意の名称(この名称を接頭辞とするオブジェクトが作成されます) まずはtestとかで結構です
    - **test_case_num**
        - 任意のテスト番号 まずは01とかで結構です
3. REPOSITORY タブに移動します
4. My Drive -> Oracle Compute Cloud Service -> Authentication -> Authentication User を選択します
5. 右のフィールドにある Send というボタンを押します
6. 応答 が 204 No Content で帰ってきていることを確認します  
   また、Response Body が No Content であることも確認します  
   ※もし上記以外の応答が帰ってきている場合には、2の変数に間違った値(異なるエンドポイントや認証)が入っていることが考えれられますので、再度見直してください
7. あとは、各RESTのエンドポイントAccount ~ Storage Volumes までを自由にコールすることができます  
   まずは 各RESTエンドポイントのうち Retrieve Details of all XXXX in a Container というGETのAPIをコールして、既に定義されている各オブジェクトを確認してみてください
8. Create や Delete をする場合には、2の変数で定義した test_case_name および test_case_num を使用しますので、必要に応じてここを書き換えてください
9. オブジェクトを作成すると、Compute Cloud のサービスコンソールから確認することができます

## リンク
- [Restlet DHC](https://restlet.com/products/dhc/)
- [Oracle Cloud](https://cloud.oracle.com/home)
- [Oracle Compute Cloud REST API](https://docs.oracle.com/cloud/latest/stcomputecs/STCSA/toc.htm)
