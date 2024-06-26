### [インデックス検索](https://redmine.devops.rcos.nii.ac.jp/projects/weko-dev-doc/wiki/%E3%82%A4%E3%83%B3%E3%83%87%E3%83%83%E3%82%AF%E3%82%B9%E3%83%84%E3%83%AA%E3%83%BC%E6%A4%9C%E7%B4%A2)

  - > 目的・用途

本機能は、ユーザーが「インデックスツリー」エリアまたは、「インデックスリンク」エリアからインデックスを選択してアイテムを検索する際に用いる機能である。  
選択したインデックスに所属するアイテムを検索することができる。

  - > 利用方法

メインコンテンツ」ウィジェットの［トップ（Top）］タブにある［インデックスツリー］エリア、または「インデックスリンク」エリアを使用する。インデックス名を選択することで、選択したインデックスに所属するアイテムを検索する。

  - > 利用可能なロール

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
<td>○</td>
<td>○</td>
</tr>
</tbody>
</table>

  - > 機能内容

<!-- end list -->

  - 設定されているインデックスツリーが存在し、インデックスリンク表示を有効に設定している時、トップページ画面の［インデックスツリー(Index Tree)］エリアの上部に［インデックスリンク(Index Link)］エリアを表示する。
    
      - ［インデックスリンク］エリアは［インデックスツリー］エリアと同じ表示幅で表示する。
    
      - 【Administration \> インデックスツリー管理 \> ツリー編集（Edit Tree）】画面にてインデックスツリーを追加することができる。詳細は[ADMIN-3-1 ツリー編集](\\l)を参照すること。
    
      - ［インデックスリンク］エリアの表示設定は【Administration \> 設定（Setting） \> インデックスリンク表示（Index Link）画面】で行う。設定については[ADMIN-14-2: インデックスリンク表示](#インデックスリンク表示)を参照。
        
          - デフォルト設定：無効

  - ［インデックスリンク］エリアには、インデックスリンク表示を有効に設定しているインデックスをプルダウンの選択肢として表示する。
    
      - インデックスごとのインデックスリンクの表示設定は【Administration \> インデックスツリー(Index Tree)管理 \> ツリー編集（Edit Tree）画面】で行う。設定については[ADMIN-3-1: ツリー編集](#ツリー編集)を参照すること。
        
          - デフォルト設定：すべての初期設定されるインデックスについて無効
        
          - 表示名の言語は「英語」「日本語」とする。
        
          - 表示画面で指定した言語の言語リソースが設定されていない場合は英語表示とする。
    
      - ユーザーの閲覧権限があるインデックスを「インデックスリンク」プルダウンに表示する。
    
      - 親インデックスに閲覧権限がなく、その親に連なる子インデックスに閲覧権限がある場合、子インデックスのインデックスリンクは表示されない。

  - 設定されているインデックスツリーが存在し、インデックスツリーを表示する設定にしている場合、トップページ画面［トップ（Top）］タブ内の［インデックスツリー（Index Tree）］エリアに、各インデックスへのリンクを表示する。
    
      - 【Administration \> インデックスツリー管理 \> ツリー編集（Edit Tree）】画面にてインデックスツリーを追加、編集、設定することができる。詳細は[ADMIN-3-1 ツリー編集](#_ツリー編集)を参照すること。
    
    <!-- end list -->
    
      - インデックスツリーの表示設定は【Administration \> 設定（Setting） \> 検索設定（Search）画面】の［インデックスツリー／ファセット表示設定］エリアでの設定に応じて表示される。設定については[ADMIN-14-11: 検索設定](#検索設定)を参照すること。
        
          - インデックスツリーのデフォルト表示設定：表示（Display）
    
    <!-- end list -->
    
      - インデックスが子インデックスを持つ場合、インデックスの左の図形▶をクリックすると、子インデックスへのリンクを当該インデックスの下に表示する。再度クリックすると子インデックスを非表示とする。
    
      - インデックスが子インデックスを持たない場合、インデックスの左の図形は▷とする。
    
      - ［インデックスツリー（Index Tree）］エリアの見出しのリンク［インデックスツリー］は、「Root Index」へのリンクとする。
    
      - > 閲覧権限を持たないユーザーに対しては、非公開インデックスは表示しないものとする。
    
      - 親インデックスに閲覧権限がなく、その親に連なる子インデックスに閲覧権限がある場合、親だけでなく子インデックスのインデックスリンクも表示されない。
    
      - ツリー編集画面にて「表示範囲」項目を設定している場合、設定された数を超える子インデックスは初回で表示されず、\[more...\]を押すことでそれらが表示されるようになる。詳細は[ADMIN-3-1 ツリー編集](#_ツリー編集)を参照すること

  - ［インデックスツリー（Index Tree）］エリアのリンク、または\[インデックスリンク\]エリアのプルダウンを押下すると、当該インデックスに所属する子インデックスとアイテムを検索できる。
    
      - トップページ画面［トップ］タブ内の［Index List］エリアに選択したインデックスに所属するインデックスのリストを、［アイテムリスト］エリアに選択したインデックスに所属するアイテムのリストを表示する。
    
      - > 閲覧権限を持たないユーザーに対しては、検索結果に非公開インデックスは表示しないものとする。

<!-- end list -->

  - > ［Index List］エリア
    
      - エリア内の上部にパンくずリストを表示する。  
        パンくずリストのリンクを押下すると、上位のインデックスへ遷移可能とする。  
        なお、「Root Index」の場合はパンくずリストを表示しない。
    
      - > 選択したインデックスに所属する子インデックスのリストを表示する。
        
          - 各インデックスをリンク形式で以下のテンプレートのように表示する。  
            リンクをクリックすると、当該インデックスを検索条件としたアイテム検索を実施する。

> テンプレート：
> 
> インデックス名 + 空白文字 + "\<" + インデックスID + "\>"

  - インデックスIDはリポジトリ管理者以上の権限のみに対して表示する。

<!-- end list -->

  - 各インデックスに所属しているアイテムの公開アイテム件数と非公開のアイテム及び、公開日が未来であるアイテムの合計件数をPrivateのアイテム件数として表示する。なお、ゲストユーザーの場合、非公開のアイテム件数は表示されず、表示可能なアイテムの件数を表示する。
    
      - 子インデックスがあれば、全ての子インデックスに所属しているアイテムの件数を取得する。
    
      - 非公開のインデックスであれば、そのインデックスに所属しているアイテムを非公開のアイテムとして数える。

  - インデックスの初期表示設定が「Root Index」のとき、または［インデックスツリー］エリアの見出しのリンク［インデックスツリー］を押下したとき、［インデックスリスト(Index List)］エリアに「Root Index」の子インデックスのリストが表示され、パンくずリストは表示しない。  
    ※コミュニティ画面の「Root Index」は［アイテムリスト(Item Lists)］エリアを表示する。

  - 「Root Index」以外の最下層でないインデックスを表示した際、［インデックスリスト(Index List)］エリアにはパンくずリストと下位のインデックスを表示する。
    
      - 該当インデックスにリンクするアイテムがある場合はアイテムリストにアイテムを表示する。
    
      - 該当インデックスにリンクするアイテムが無い場合はアイテムリストのエリアのみ表示する。

  - 「Root Index」以外の最下層のインデックスを表示した際、［インデックスリスト(Index List)］エリアにはパンくずリストを表示する。
    
      - 該当インデックスにリンクするアイテムがある場合はアイテムリストにアイテムを表示する。
    
      - 該当インデックスにリンクするアイテムが無い場合はアイテムリストのエリアのみ表示する。

  - 検索結果は、【Administration \> インデックスツリー管理 \> ツリー編集（Edit Tree）画面】の［表示形式(検索結果) ］（Display Format(Search Results)）の設定に応じて表示される。設定については[ADMIN-3-1: ツリー編集](#ツリー編集)を参照すること。
    
      - 「一覧形式」（List）
        
          - インデックスリスト
        
          - インデックス.サムネイル画像
        
          - インデックス雑誌情報  
            （【Administration \> インデックスツリー管理 \> 雑誌情報　画面】で該当インデックスの雑誌情報を出力する設定がされている場合のみ表示される。）
        
          - インデックスコメント
        
          - 表示しているインデックスの検索URL  
            インデックス雑誌情報を出力する設定がされている場合のみ表示される。
        
          - アイテムリスト（一覧形式）
    
      - 「目次形式」（Table Of Contents）
        
          - インデックスリスト
        
          - インデックスサムネイル画像
        
          - インデックスコメント
        
          - アイテムリスト（目次形式）

  - インデックス雑誌情報としては、雑誌情報を登録済みであり、【Administration \> インデックスツリー管理 \> 雑誌情報　画面】で「出力する」に設定されている場合のみ、以下の雑誌情報を初期表示する。雑誌情報の登録、設定については[ADMIN-3-2: 雑誌情報](#雑誌情報-1)を参照すること。
    
      - 雑誌名
    
      - 出版者
    
      - 言語
    
      - eISSN / eISBN
    
      - 表示しているインデックスの検索URL
    
      - その他の登録されている雑誌情報は、初期表示では［▷詳細］リンクを表示し、非表示とする。［▷詳細］リンクをクリックすると、情報が表示される。詳細は[USER-2-3 雑誌情報](#雑誌情報-1)を参照すること

  - インデックスサムネイル画像は、【Administration \> インデックスツリー管理(Index Tree) \> ツリー編集（Edit Tree）画面】に設定されたサムネイル画像から取得し、表示する。

<!-- end list -->

  - インデックスコメントは、【Administration \> インデックスツリー管理(Index Tree) \> ツリー編集（Edit Tree）画面】に設定された「コメント」（Comment）から取得し、表示する。［アイテムリスト］エリア
    
      - インデックスに所属するアイテムの検索結果を表示する。
    
      - アイテムリストの表示についての詳細は  
        一覧形式表示の際は[USER-2-1一覧形式表示](#一覧形式表示)を、目次形式表示の際は[USER-2-2 目次形式表示](#目次形式表示)を参照すること。デフォルトでは一覧形式表示で表示される。

<!-- end list -->

  - > 関連モジュール

<!-- end list -->

  - > weko\_search\_ui：検索結果をUIに表示する

  - > weko\_index\_tree

  - > weko\_theme

  - 
<!-- end list -->

  - > 処理概要

<!-- end list -->

  - インデックスリンクを表示する設定にしている時に、トップページ画面にアクセスする。  
    この操作によって、weko\_theme.views.indexメソッドにてget\_weko\_contentsを呼び出し、更にget\_index\_link\_listを呼び出して、インデックスリンクの情報を取得し、プルダウンに表示する。
    
      - なお、インデックスリンクがONになっているか否かはget\_index\_link\_listメソッドで確認する。

  - インデックスツリーを表示する設定にしている場合、トップページ画面にアクセスする。  
    この操作によって、weko\_index\_tree.rest.getメソッドにてget\_browsing\_treeメソッドまたは、get\_more\_browsing\_treeメソッドで設定されたインデックスツリー情報をredisから取得し、「インデックスツリー」エリアを表示する。
    
      - なお、インデックスツリーの表示は以下のソースコードを元にしている。<https://github.com/RCOSDP/weko-angular/blob/master/app-tree-items-detail/src/app/tree-list2/tree-list2.component.html>
    
    <!-- end list -->
    
      - > ［インデックスツリー］エリアには、現在設定されているインデックスツリーのリンクを表示する。
    
      - > 閲覧権限のないインデックスはweko\_index\_tree.utils. reduce\_index\_by\_roleメソッドにてroleにアクセス権限がないインデックスを非表示とする。
    
    <!-- end list -->
    
      - インデックスが子インデックスを持つ場合、インデックスの左の図形▶をクリックすると、子インデックスへのリンクを当該インデックスの下に表示し、図形を▼に変化させる。再度図形▼をクリックすると子インデックスを非表示とする。

> メインコンテンツ」ウィジェットの［トップ（Top）］タブ内に表示される、［インデックスツリー］エリア内のインデックスのリンクを押下する、または、\[インデックスリンク\]エリアのプルダウンからインデックスを選択する。この操作によって以下の処理をする。

  - > weko\_search\_ui.static.js.weko\_search\_ui.app getPathNameメソッドを呼び出す。そして、get\_path\_name\_dictメソッドによってindexテーブルより選択したインデックスのパンくずリストを取得する。なお、権限がないインデックスはfilter\_index\_list\_by\_roleメソッドで非表示になる。

  - > 検索結果の表示設定が一覧形式の時、選択したインデックスに登録されている公開設定の雑誌情報をweko\_search\_ui.views.searchメソッドにてget\_journal\_infoを使って取得し、表示する。処理の詳細についてはUSER-2-3雑誌情報を参照すること

  - > weko\_search\_ui.static.js.weko\_search\_ui.app.getChildListメソッドを呼び出す。そして、get\_child\_listメソッドによってindexテーブルより選択したインデックスに所属する子インデックスのデータを取得し、表示する。

  - > weko\_search\_ui.static.js.weko\_search\_ui.app.dispaly\_comment\_journalメソッドにて、format\_commentを呼び出し、コメントを整形し表示する。

  - > weko\_search\_ui.rest.IndexSearchResource.getメソッドにて、searchインスタンスで処理を行い、インデックスに所属するアイテムの情報を取得する。

  - > invenio\_records\_rest.serializers.response.search\_responsifyメソッドを呼び出し、アイテムリストにて表示する情報(リンク、メタデータ表示設定など)を取得する。

> ［アイテムリスト］エリア
> 
> 取得してある該当インデックスに所属するアイテム情報を表示する。

  - > アイテムリストについての処理概要は一覧形式表示の際はUSER-2-1一覧形式表示を、目次形式表示の際はUSER-2-2 目次形式表示を参照してください。デフォルトでは一覧形式表示で表示されます。

<!-- end list -->

  - > 更新履歴

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
<p>2022/05/10</p>
</blockquote></td>
<td>57247ecce9b5e0879a2538687e446e0ea310129c</td>
<td>初版作成</td>
</tr>
<tr class="even">
<td><blockquote>
<p>2023/08/31</p>
</blockquote></td>
<td>353ba1deb094af5056a58bb40f07596b8e95a562</td>
<td>v0.9.22対応</td>
</tr>
</tbody>
</table>
