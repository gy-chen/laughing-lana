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

NoteStorage
===========

負責註記資料的永久儲存與取得，以timestamp作為辨識，每個不同的timestamp皆為
不同的註記資料。

NoteStorage的資料輸出格式可以為資料庫的Cursor或是JSon型態資料。