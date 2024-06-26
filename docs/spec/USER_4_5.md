### Item Registration：ファイルアップロード

#### 目的・用途

Item Registrationの一部として、ファイルをアップロードしてそのファイルの情報を設定する。

#### 利用方法

ファイルのプロパティが指定されているアイテムタイプのアイテム登録、編集を行うワークフローで、Item Registration画面を表示する。

#### 利用可能なロール

<table>
<thead>
<tr class="header">
<th>ロール</th>
<th>システム<br />
管理者</th>
<th>リポジトリ<br />
管理者</th>
<th>コミュニティ<br />
管理者</th>
<th>登録ユーザー</th>
<th>一般ユーザー</th>
<th>ゲスト<br />
(未ログイン)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>利用可否</td>
<td>○</td>
<td>○</td>
<td>○</td>
<td>○</td>
<td>※</td>
<td></td>
</tr>
</tbody>
</table>

※一般ユーザーは、ロールとして利用可能に設定することはできないが、個別のユーザーをAction Userとして設定することはできる。

#### 機能内容

1\. ファイルを登録する

  - ファイルのプロパティが指定されているアイテムタイプのアイテム登録画面にファイル登録のエリアを表示する
    
      - ファイルおよび課金ファイル情報の入力エリアをアップロードエリア直下に表示する
        
          - 表示位置を固定する
        
          - 入力エリアを開閉できる

  - ファイル登録を以下のように実施する
    
      - ファイル登録
        
          - ファイル登録のエリアに「Click to select」ボタンを押すと、アップロードファイル選択ダイヤログを表示する
            
              - アップロードするローカルファイルを選択し、「Open」ボタンを押すと、選択されたファイルをファイル登録のエリアに追加する
            
              - 複数ファイルを選択できる
        
          - 「Drop files or folders here」のテキストボックスにドラッグ&ドロップすることでもファイルを追加できる
        
          - ファイルを追加した後、以下のようなファイルの情報を表示する
            
              - Filename：追加したファイル名
            
              - Size：ファイル容量のバイト
            
              - Progress：空白
            
              - Actions：ごみ箱ボタン
        
          - ファイル追加時に全文テキスト抽出対象（WEKO\_MIMETYPE\_WHITELIST\_FOR\_ES）の場合は抽出処理を行う。抽出後の全文テキスト合わせてElasticsearchのhttp.max_content_length（デフォルトは100MB）以下である必要がある。
        
          - 追加したファイルを削除する場合、ファイル行での「Actions」にあるごみ箱ボタンを押すと、該当ファイルを削除する
    
      - ファイル編集
        
          - 一括登録を実行中に他端末および実行端末でアイテムの\[編集\]ボタンを押下した場合  
            日本語：インポートを実行中のためアイテムの編集はできません。  
            英語：Item cannot be edited because the import is in progress.
    
      - ファイル削除
        
          - 一括登録を実行中に他端末および実行端末でアイテムの\[削除\]ボタンを押下した場合  
            日本語：インポートを実行中のためアイテムの削除はできません。  
            英語：Item cannot be deleted because the import is in progress.
    
      - ファイル差し替え
        
          - インポート機能による本文ファイルの差し替えの場合  
            以下の条件でアイテムのコンテンツファイルを編集すると、統計情報を引き継いで更新される  
            .file\_path \[xx\] を書き換え  
            該当ディレクトリにコンテンツファイルを配置  
            .metadata.item\_files \[xx\] .filename を書き換え  
            ファイル名が同名か、異なる名前かに関わらず、上記の条件でインポートファイルを作成した場合はファイルの差し替えとなる
            
              - \[xx\] は該当のアイテムにファイルが複数ある場合を考慮すること。また、ファイルの追加・削除に影響がないこと
        
          - 個別編集による本文ファイルの差し替えの場合  
            同名ファイル、または異なるファイル名で差し替えをする場合、Item Registrationのファイル情報プロパティでファイル名を選択するときに、差し替え後のファイル名がプルダウンで表示される
    
      - ファイルアップロード
        
          - 「Start upload」ボタンを押すと、追加しているファイルのアップロードを行う
            
              - 「Cancel」ボタンを「Start upload」ボタンの左側に表示する  
                「Cancel」ボタンを押すと、アップロードが強制中止する
            
              - ファイルでの「Progress」にアップロードの進捗を表示する
                
                  - アップロード中：アップロードのパーセントを表示する
                
                  - アップロード済み：  
                    成功の場合：「✓」アイコンを表示する  
                    失敗の場合：「Error 」を表示する
        
          - アップロードが完了すると、アップロードしたファイル名を「ファイル名」に自動設定する  
            ファイルが複数の場合は、ファイル情報入力エリアをその数分追加した上でそれぞれ設定する  
            ［Start upload］ボタンは非活性化する
    
      - マルチパートファイルアップロード
        
          - 定数「 FILES\_REST\_USE\_MULTIPART\_UPLOAD 」によって、マルチパートアップロード機能を有効にする。
        
          - 定数「 FILES\_REST\_RESUME\_CHUNK\_SIZE 」によって、マルチパートアップロード機能が用いられるファイルサイズの閾値を設定する。（閾値を下回る場合は、通常のファイルアップロードとなる）
        
          - 「Start upload」ボタンを押すと、追加しているファイルのアップロードを行う
            
              - 「Cancel」ボタンを「Start upload」ボタンの左側に表示する  
                「Cancel」ボタンを押すと、アップロードが強制中止する
            
              - ファイルでの「Progress」にアップロードの進捗を表示する
                
                  - レジュームチェック中：「Resuming...」を表示する
                
                  - アップロード完了処理中：「Processing...」を表示する
                
                  - アップロード中：アップロードのパーセントを表示する
                
                  - アップロード済み：  
                    成功の場合：「✓」アイコンを表示する  
                    失敗の場合：「Error 」を表示する。「Resume」ボタンを表示する。
        
          - アップロードが完了すると、アップロードしたファイル名を「ファイル名」に自動設定する  
            ファイルが複数の場合は、ファイル情報入力エリアをその数分追加した上でそれぞれ設定する  
            ［Start upload］ボタンは非活性化する
        
          - 「Resume」ボタン押下し、ファイルを再選択すると、失敗したファイルアップロードを再開できる。再開できる期間には、限度があり、 定数「FILES\_REST\_MULTIPART\_EXPIRES」で定義される。この定数は、ObjectStorageのライフサイクル期間の日付と合わせる必要がある。
    
      - ファイル情報の入力
        
          - コンテンツファイルについて
            
              - 「表示名」（FileName）
            
              - 「本文URL」（Text URL）
            
              - 「ラベル」（Lable）  
                アイテム詳細画面に表示するファイルのリンク名
            
              - 「オブジェクトタイプ」（Object Type）  
                選択肢：統制語彙（https://schema.irdb.nii.ac.jp/ja/schema/1.0.2/35-.1）
            
              - 「フォーマット」（Format）
                
                  - ファイル名で、WEKO3にアップロードされたファイルが選択された場合は、そのファイルのフォーマット（mimeType）を判定して表示する
                
                  - システムで判定した値をユーザが修正することができるよう、テキストボックスにする
            
              - 「サイズ」（Size）
                
                  - ファイル名で、WEKO3にアップロードされたファイルが選択された場合は、そのファイルのサイズを判定して表示する
                
                  - システムで判定した値をユーザが修正することができるよう、テキストボックスにする
                
                  - 繰り返し可能であるようにする
            
              - 「日付」（Date）
                
                  - 日付のエリアは「日付タイプ」（Date Type）と「日付」（Date）を入力するエリア（カレンダーを表示する）を持つ
                
                  - 日付タイプには日付の統制語彙を選択できるようにするが、Availableは選択肢に含めない
                
                  - 繰り返し可能であるようにする
            
              - 「バージョン情報」（Version Information）
            
              - 「表示形式」（Preview）  
                選択肢：「詳細表示」（Detail）、「簡易表示」（Simple）、「プレビュー」（Preview）
            
              - 「ライセンス」（License）  
                選択肢：Creative Commonsのライセンス表記を設定できる、かつ自由に記述できる  
                Creative Commonsのライセンス表記：コンフィグファイルから取得する
                
                  - コンフィグでの設定の詳細は処理概要を参照
            
              - 「アクセス」（Access）
                
                  - オープンアクセス（Open Access）
                
                  - オープンアクセス日を指定する（Input Open Access Date）
                    
                      - オープンアクセス日を指定する必要がある
                
                  - ログインユーザーのみ（Registered User Only）
                    
                      - ユーザーグループを指定する必要がある
                
                  - 公開しない（Do not Publish）
                
                  - 制限公開（Limited Access）
                    
                      - コンテンツファイルのプロパティで定義されている場合のみ表示
                    
                      - 「制限公開」を選択している際は以下の項目を表示する
                        
                          - ［データタイプ］：プロパティ内で定義している選択肢を表示する
                        
                          - ［提供方法］：アイテム詳細画面で「申請」ボタンを押下した際、どの利用申請ワークフローを起動するか設定する。複数設定できる（繰り返し可）として、以下の項目を子項目とする
                            
                              - ［ワークフロー\]：  
                                【Administration \> ワークフロー管理（WorkFlow） \> ワークフロー（WorkFlow List）画面】で管理しているワークフローのうち「制限公開フラグ」が有効なものをリストに表示する
                            
                              - ［ロール］：Admin\>UserManagement\>Roleで管理しているロールと「非ログインユーザ」をリストに表示する
                        
                          - ［利用規約］：管理画面で登録した利用規約をリストで表示する。選択肢に「自由入力」を設け、選択した際はテキストエリアを表示する
        
          - 課金ファイルについて
            
              - 「表示名」（FileName）  
                アップロードされたファイル名を選択する
            
              - 「ラベル」（Lable）  
                アイテム詳細画面に表示するファイルのリンク名
            
              - 「オブジェクトタイプ」（Object Type）  
                選択肢：統制語彙（https://schema.irdb.nii.ac.jp/ja/schema/1.0.2/35-.1）
            
              - 「バージョン情報」（Version Information）
            
              - 「表示形式」（Preview）  
                選択肢：「詳細表示」（Detail）、「簡易表示」（Simple）、「プレビュー」（Preview）
            
              - 「ライセンス」（License）  
                選択肢：Creative Commonsのライセンス表記を設定できる、かつ自由に記述できる  
                Creative Commonsのライセンス表記：コンフィグファイルから取得する　
            
              - 「アクセス」（Access）
                
                  - オープンアクセス
                
                  - オープンアクセス日を指定する（Input Open Access Date）
                    
                      - オープンアクセス日を指定する必要がある
                
                  - ログインユーザーのみ（Registered User Only）
                    
                      - ユーザーグループ及びグループごとの価格を指定する必要である
                
                  - 公開しない（Do not Publish）

2\. ファイルを差し替える

  - ファイルが添付されているアイテムを編集する際に、ファイルの差し替えを行うことができる
    
      - アイテム編集時にファイルが添付されている場合、Action欄に \[Replace\] ボタンが表示される
    
      - ファイルを差し替える場合は、\[Replace\] ボタンを押下して、差し替えるファイルを登録する
    
      - \[Replace\] ボタンを押下すると「アップロードファイル選択」ダイアログが開き、ファイルを選択すると、選択後のファイル名が画面上に赤文字で表示される。
    
      - \[Start upload\] ボタンを押下してファイルの取り込みを行うことで、差し替え前のファイル情報プロパティのファイル名、本文URL、フォーマット、サイズの情報が上書きされる

  - ファイルを差し替えた場合でも、統計情報を引き継がせる（差し替え前の値が維持されて合算される）ことができる。引き継がせるケースとしては以下の通り。
    
      - ファイルの差し替えと同時に「バージョンの変更」してアイテム更新
    
      - 「バージョンの変更」してアイテム更新後に、「keep」でファイルの差し替え

3\. ファイルのサムネイルを登録できる

  - 「サムネイル」（Thumbnail）パネルにファイルのサムネイルを登録できる
    
      - 「サムネイル」（Thumbnail）パネルに「Click to select」ボタンを押すと、アップロードファイル選択ダイヤログを表示する
        
          - 選択可能ファイルの拡張子：gif, jpg, jpe, jpeg, png, bmp
        
          - 一つのファイルのみ選択できる
        
          - 登録可能なファイル以外のファイルをアップロードしようとしたときにエラーメッセージをポップアップで表示する
            
              - 「画像ファイル（gif, jpg, jpe, jpeg, png, bmp）以外のファイルはアップロードできません」
    
      - ファイルを登録した後、以下のようなファイルの情報を表示する
        
          - ファイル名（Filename）：登録したファイル名
        
          - 容量（Size）：ファイル容量のバイト
        
          - 進捗（Progress）：「✓」アイコンを表示する
        
          - アクション（Actions）：「X」ボタン
    
      - 追加したファイルを削除する場合、「Actions」にてごみ箱ボタンを押すと、該当ファイルを削除する
    
      - ファイルが登録されている状態で、他のファイルをアップロードすると、後からアップロードしたファイルに置き換わる

<!-- end list -->

#### 関連モジュール

<!-- end list -->

- weko\_workflow

<!-- end list -->

#### 処理概要

> Creative Commonsのライセンス表記を設定する

  - > パス： <https://github.com/RCOSDP/weko/blob/v0.9.22/scripts/instance.cfg#L248>

  - > 設定キー： 「WEKO\_RECORDS\_UI\_LICENSE\_DICT」

  - > 現在の設定値：

> WEKO\_RECORDS\_UI\_LICENSE\_DICT = \[
> 
> {
> 
> 'name': \_('write your own license'),
> 
> 'value': 'license\_free',
> 
> },
> 
> \# version 0
> 
> {
> 
> 'name': \_('Creative Commons CC0 1.0 Universal Public Domain Designation'),
> 
> 'code' : 'CC0',
> 
> 'href\_ja': 'https://creativecommons.org/publicdomain/zero/1.0/deed.ja',
> 
> 'href\_default': 'https://creativecommons.org/publicdomain/zero/1.0/',
> 
> 'value': 'license\_12',
> 
> 'src': '88x31(0).png',
> 
> 'src\_pdf': 'cc-0.png',
> 
> 'href\_pdf': 'https://creativecommons.org/publicdomain/zero/1.0/'
> 
> 'deed.ja',
> 
> 'txt': 'This work is licensed under a Public Domain Dedication '
> 
> 'International License.'
> 
> },
> 
> \# version 3.0
> 
> {
> 
> 'name': \_('Creative Commons Attribution 3.0 Unported (CC BY 3.0)'),
> 
> 'code' : 'CC BY 3.0',
> 
> 'href\_ja': 'https://creativecommons.org/licenses/by/3.0/deed.ja',
> 
> 'href\_default': 'https://creativecommons.org/licenses/by/3.0/',
> 
> 'value': 'license\_6',
> 
> 'src': '88x31(1).png',
> 
> 'src\_pdf': 'by.png',
> 
> 'href\_pdf': 'http://creativecommons.org/licenses/by/3.0/',
> 
> 'txt': 'This work is licensed under a Creative Commons Attribution'
> 
> ' 3.0 International License.'
> 
> },
> 
> {
> 
> 'name': \_('Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)'),
> 
> 'code' : 'CC BY-SA 3.0',
> 
> 'href\_ja': 'https://creativecommons.org/licenses/by-sa/3.0/deed.ja',
> 
> 'href\_default': 'https://creativecommons.org/licenses/by-sa/3.0/',
> 
> 'value': 'license\_7',
> 
> 'src': '88x31(2).png',
> 
> 'src\_pdf': 'by-sa.png',
> 
> 'href\_pdf': 'http://creativecommons.org/licenses/by-sa/3.0/',
> 
> 'txt': 'This work is licensed under a Creative Commons Attribution'
> 
> '-ShareAlike 3.0 International License.'
> 
> },
> 
> {
> 
> 'name': \_('Creative Commons Attribution-NoDerivs 3.0 Unported (CC BY-ND 3.0)'),
> 
> 'code' : 'CC BY-ND 3.0',
> 
> 'href\_ja': 'https://creativecommons.org/licenses/by-nd/3.0/deed.ja',
> 
> 'href\_default': 'https://creativecommons.org/licenses/by-nd/3.0/',
> 
> 'value': 'license\_8',
> 
> 'src': '88x31(3).png',
> 
> 'src\_pdf': 'by-nd.png',
> 
> 'href\_pdf': 'http://creativecommons.org/licenses/by-nd/3.0/',
> 
> 'txt': 'This work is licensed under a Creative Commons Attribution'
> 
> '-NoDerivatives 3.0 International License.'
> 
> },
> 
> {
> 
> 'name': \_('Creative Commons Attribution-NonCommercial 3.0 Unported (CC BY-NC 3.0)'),
> 
> 'code' : 'CC BY-NC 3.0',
> 
> 'href\_ja': 'https://creativecommons.org/licenses/by-nc/3.0/deed.ja',
> 
> 'href\_default': 'https://creativecommons.org/licenses/by-nc/3.0/',
> 
> 'value': 'license\_9',
> 
> 'src': '88x31(4).png',
> 
> 'src\_pdf': 'by-nc.png',
> 
> 'href\_pdf': 'http://creativecommons.org/licenses/by-nc/3.0/',
> 
> 'txt': 'This work is licensed under a Creative Commons Attribution'
> 
> '-NonCommercial 3.0 International License.'
> 
> },
> 
> {
> 
> 'name': \_('Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported (CC BY-NC-SA 3.0)'),
> 
> 'code' : 'CC BY-NC-SA 3.0',
> 
> 'href\_ja': 'https://creativecommons.org/licenses/by-nc-sa/3.0/deed.ja',
> 
> 'href\_default': 'https://creativecommons.org/licenses/by-nc-sa/3.0/',
> 
> 'value': 'license\_10',
> 
> 'src': '88x31(5).png',
> 
> 'src\_pdf': 'by-nc-sa.png',
> 
> 'href\_pdf': 'http://creativecommons.org/licenses/by-nc-sa/3.0/',
> 
> 'txt': 'This work is licensed under a Creative Commons Attribution'
> 
> '-NonCommercial-ShareAlike 3.0 International License.'
> 
> },
> 
> {
> 
> 'name': \_('Creative Commons Attribution-NonCommercial-NoDerivs 3.0 Unported (CC BY-NC-ND 3.0)'),
> 
> 'code' : 'CC BY-NC-ND 3.0',
> 
> 'href\_ja': 'https://creativecommons.org/licenses/by-nc-nd/3.0/deed.ja',
> 
> 'href\_default': 'https://creativecommons.org/licenses/by-nc-nd/3.0/',
> 
> 'value': 'license\_11',
> 
> 'src': '88x31(6).png',
> 
> 'src\_pdf': 'by-nc-nd.png',
> 
> 'href\_pdf': 'http://creativecommons.org/licenses/by-nc-nd/3.0/',
> 
> 'txt': 'This work is licensed under a Creative Commons Attribution'
> 
> '-NonCommercial-ShareAlike 3.0 International License.'
> 
> },
> 
> \# version 4.0
> 
> {
> 
> 'name': \_('Creative Commons Attribution 4.0 International (CC BY 4.0)'),
> 
> 'code' : 'CC BY 4.0',
> 
> 'href\_ja': 'https://creativecommons.org/licenses/by/4.0/deed.ja',
> 
> 'href\_default': 'https://creativecommons.org/licenses/by/4.0/',
> 
> 'value': 'license\_0',
> 
> 'src': '88x31(1).png',
> 
> 'src\_pdf': 'by.png',
> 
> 'href\_pdf': 'http://creativecommons.org/licenses/by/4.0/',
> 
> 'txt': 'This work is licensed under a Creative Commons Attribution'
> 
> ' 4.0 International License.'
> 
> },
> 
> {
> 
> 'name': \_('Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)'),
> 
> 'code' : 'CC BY-SA 4.0',
> 
> 'href\_ja': 'https://creativecommons.org/licenses/by-sa/4.0/deed.ja',
> 
> 'href\_default': 'https://creativecommons.org/licenses/by-sa/4.0/',
> 
> 'value': 'license\_1',
> 
> 'src': '88x31(2).png',
> 
> 'src\_pdf': 'by-sa.png',
> 
> 'href\_pdf': 'http://creativecommons.org/licenses/by-sa/4.0/',
> 
> 'txt': 'This work is licensed under a Creative Commons Attribution'
> 
> '-ShareAlike 4.0 International License.'
> 
> },
> 
> {
> 
> 'name': \_('Creative Commons Attribution-NoDerivatives 4.0 International (CC BY-ND 4.0)'),
> 
> 'code' : 'CC BY-ND 4.0',
> 
> 'href\_ja': 'https://creativecommons.org/licenses/by-nd/4.0/deed.ja',
> 
> 'href\_default': 'https://creativecommons.org/licenses/by-nd/4.0/',
> 
> 'value': 'license\_2',
> 
> 'src': '88x31(3).png',
> 
> 'src\_pdf': 'by-nd.png',
> 
> 'href\_pdf': 'http://creativecommons.org/licenses/by-nd/4.0/',
> 
> 'txt': 'This work is licensed under a Creative Commons Attribution'
> 
> '-NoDerivatives 4.0 International License.'
> 
> },
> 
> {
> 
> 'name': \_('Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)'),
> 
> 'code' : 'CC BY-NC 4.0',
> 
> 'href\_ja': 'https://creativecommons.org/licenses/by-nc/4.0/deed.ja',
> 
> 'href\_default': 'https://creativecommons.org/licenses/by-nc/4.0/',
> 
> 'value': 'license\_3',
> 
> 'src': '88x31(4).png',
> 
> 'src\_pdf': 'by-nc.png',
> 
> 'href\_pdf': 'http://creativecommons.org/licenses/by-nc/4.0/',
> 
> 'txt': 'This work is licensed under a Creative Commons Attribution'
> 
> '-NonCommercial 4.0 International License.'
> 
> },
> 
> {
> 
> 'name': \_('Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)'),
> 
> 'code' : 'CC BY-NC-SA 4.0',
> 
> 'href\_ja': 'https://creativecommons.org/licenses/by-nc-sa/4.0/deed.ja',
> 
> 'href\_default': 'https://creativecommons.org/licenses/by-nc-sa/4.0/',
> 
> 'value': 'license\_4',
> 
> 'src': '88x31(5).png',
> 
> 'src\_pdf': 'by-nc-sa.png',
> 
> 'href\_pdf': 'http://creativecommons.org/licenses/by-nc-sa/4.0/',
> 
> 'txt': 'This work is licensed under a Creative Commons Attribution'
> 
> '-NonCommercial-ShareAlike 4.0 International License.'
> 
> },
> 
> {
> 
> 'name': \_('Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0)'),
> 
> 'code' : 'CC BY-NC-ND 4.0',
> 
> 'href\_ja': 'https://creativecommons.org/licenses/by-nc-nd/4.0/deed.ja',
> 
> 'href\_default': 'https://creativecommons.org/licenses/by-nc-nd/4.0/',
> 
> 'value': 'license\_5',
> 
> 'src': '88x31(6).png',
> 
> 'src\_pdf': 'by-nc-nd.png',
> 
> 'href\_pdf': 'http://creativecommons.org/licenses/by-nc-nd/4.0/',
> 
> 'txt': 'This work is licensed under a Creative Commons Attribution'
> 
> '-NonCommercial-ShareAlike 4.0 International License.'
> 
> },
> 
> \]

#### 実装方法

#### 更新履歴

<table>
<thead>
<tr class="header">
<th>日付</th>
<th>GitHubコミットID</th>
<th>更新内容</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><blockquote>
<p>2023/08/31</p>
</blockquote></td>
<td>353ba1deb094af5056a58bb40f07596b8e95a562</td>
<td>初版作成</td>
</tr>
</tbody>
</table>
