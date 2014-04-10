Note
====

註記功能的設計說明。

NoteActivity
============

使用者註記資料的地方，NoteActivity提供三種工具給使用者註記資料，工具分別為
畫布、相片和文字編輯區，畫布提供一個區域讓使用者能使用觸控的方式繪製其觸控
的軌跡; 相片工具能讓使用者新增從行動裝置相機拍下的內容; 文字編輯區域能讓使
用者使用內建的輸入法輸入文字。當使用者輸入好要註記的資料，此Activity會將其
註記儲存，使用者往後可讀取先前儲存的內容，並再進一步編輯。

啟用NoteActivity
----------------

NoteActivity沒有設定<intent-filter>，因此需使用指定類別的Intent來啟用它，
啟用NoteActivity可選帶Extra資料NoteActivity.EXTRA_NOTE_TIMESTAMP，此Extra
資料可指定讀取的註記簿，如果未傳入此資料，NoteActivity預設會使用目前時間創造
一個新的註記簿。

NoteStorage
===========

負責註記資料的永久儲存與取得，以timestamp作為辨識，每個不同的timestamp皆為
不同的註記資料。

NoteStorage的資料輸出格式可以為資料庫的Cursor或是JSon型態資料。

註記資料轉換JSON
================

註記資料轉換的JSON格式為：

::

  {"timestamp": 筆記簿的timestamp,
    "title": 筆記簿標題
    "content": [{ "index": 筆記順序, "content": 筆記內容, "type": 筆記種類},
    ...]
  }

筆記種類的代表意義為：

::

  1 => 文字
  2 => 畫布
  3 => 相片

筆記內容皆用Base64轉換成ASCII可編碼內容。
