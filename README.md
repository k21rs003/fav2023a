1. Composerをインストール

2. fav2023フォルダに入って、以下のコマンドで、パッケージインストール
  $ composer install

3. yaml.phpを実行
  http://localhost/fav2023/yaml.php

4. -----空き状況表示プログラムのプログラム仕様------
5. ユーザーが送信したフォームデータから、年($_POST['year'])、月($_POST['month'])、日($_POST['day'])を取得します。
2. getWeekday($date)関数を使用して、指定された日付の曜日を取得します。
3. $firstDayOfMonth変数には、指定された年月の1日の曜日が数値として格納されます（日曜日から土曜日まで、0から6の範囲で表されます）。
4. $lastDayOfMonth変数には、指定された年月の最終日が格納されます。
5. "[空き状況確認]"というメッセージを表示します。
6. フォームデータから施設の選択肢($_POST['facility'])を取得し、施設名($facilityName)を決定します。
7. 土曜日と日曜日を表す配列$holidayWdaysを定義します。
8. $dが0の場合（日付が指定されていない場合）、指定された年月のカレンダーを表示します。
  ・"検索: 年月"というメッセージを表示します。
  ・$lastDayOfMonthの範囲で、各日に対して以下の処理を繰り返します。 
    ・各日の曜日を取得し、$currentDayWeekに格納します。
    ・日付を整形し、$dateKeyに格納します。
    ・$spHoliday配列から、特定の日付に該当する祝日の名前($holidayName)を取得します。もし祝日が該当しない場合は空文字列になります。
    ・$facility配列から、特定の日付に該当する施設の予約データ($reserveData)を取得します。予約データが存在しない場合は空の配列になります。
    ・日付を表示します。
    ・祝日に該当する場合は、祝日の名前とタイプを表示します。
    ・土曜日または日曜日に該当する場合は、定休日として表示します。
    ・上記のいずれにも該当しない場合は、施設の予約データが存在し、かつ予約データの施設名が指定された施設名と一致する場合、該当する時間帯を表示します。
    ・施設名が指定されていない場合、予約データが存在する場合は、予約されている施設名と時間帯を表示します。
9. $dが0でない場合（日付が指定されている場合）、指定された日付の空き状況を表示します。
  ・"検索: 年月日(曜日)"というメッセージを表示します。
  ・$spHoliday配列から、特定の日付に該当する祝日の名前($holidayName)を取得します。もし祝日が該当しない場合は空文字列になります。
  ・$facility配列から、特定の日付に該当する施設の予約データ($reserveData)を取得します。予約データが存在しない場合は空の配列になります。
  ・祝日に該当する場合は、祝日の名前とタイプを表示します。
  ・土曜日または日曜日に該当する場合は、定休日として表示します。
  ・上記のいずれにも該当しない場合は、施設の予約データが存在し、かつ予約データの施設名が指定された施設名と一致する場合、該当する時間帯を表示します。
  ・施設名が指定されていない場合、予約データが存在する場合は、予約されている施設名と時間帯を表示します。
以上がこのプログラムの基本的な仕様です。ユーザーが指定した日付や施設に応じて、対応する空き状況や予約情報を表示することが目的となります。
