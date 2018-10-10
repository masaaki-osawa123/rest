# iTunesAPIに対しRestを行い、戻り値を画面に表示するアプリ 

アーティスト名を入れて検索ボタンを押下するとRest処理が動作する。  
該当するアーティストが居た場合、そのアーティスト情報が返却される。  
返却された値のうち、ジャケット（img)、アーティスト名、曲名を画面に表示している。  
ジャケットアドレス、曲名をDBに登録している。（返却結果をDB登録処理の動作確認のため）  
 
GitHubとServiceNowを連携させる方法についてはBacklogに資料を置いたのでそちらを参照  
https://ppat-spf.backlog.jp/wiki/AOS/Git+hub%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6  
  
  
# 処理作成の流れ  

## RestMessageの作成   
　Studioメニュー「Outbound Integrations」の中から「REST Message」を選択する。  
　Endpoint、QueryParameter(引数)を設定し対象に接続できることを確認する。  
　Variableを作成するため、「Auto-generate variables」リンクを押下する。  
　「Related Links」の「Test」を選択し、テスト結果として200が返却されれば成功。  
　～ここまでが接続に関する部分～  
  
  
## UI Pageの作成  
　RestMessageを呼び出す＆検索結果を表示する画面を作成する。  
　Studioメニュー「UI Page」の中から「Create」選択。  
　HTMLに画面情報を設定。  
  「Processing script」に呼び出すRestを記載、後はサーバーサイドで行っておきたい処理を記載する。   
  
  
## Tableの作成  
　Rest結果をため込む為のTableを作成する。    
　Studioメニュー「Data Model」の中から「Table」を選択する。  
　※細かい記載は割愛とする。  
  
  
## Navigatorの作成（上記実行用)    
　RestMessage、UI Pageを呼び出すためのNavigationを作成する。  
　「Navigation」の中から「Application Menu」を選択する。  
　Module横のNewボタンを選択し、Moduleを作成する。  
　「Application menu」にて、作成したテーブルを選択する。  
  
  
## 動作確認    
　Filter Navigatorで作成したNavigatorを検索する。  
　正しく表示されたら完了。  
