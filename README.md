redmine2confluence-wiki
=======================

Redmine wikiからConfluenceにデータをインポートするためのスクリプトです。

参考:
- Tim Jansen's gist https://gist.github.com/tim-jansen/6263586 
- Stefan Bühler's redmine export script: http://stbuehler.de/blog/article/2011/06/04/exporting_redmine_wiki_pages.html

使い方:
----------
変換方法:
- Redmine環境の上で、 `exportwiki.rb` を使って `ExportWiki.export_all` を実行します。プロジェクトデータのフォルダが作成されます。
- `redmine_spaces.py` ファイルを編集します
	* provide reference to Jira ticket link conversion or another ticketing system (it will replace \g<1> with original redmine ID)
    * RedmineのプロジェクトからConfluenceのスペースへのマッピングを設定するため。異なるプロジェクトを同一のスペースにマッピングすることも可能です。その場合、コンフリクトしたページは無視されます。
- `import_confluence.py` を編集して以下を設定します
	* user name
	* password
	* confluence URL
- エクスポートされたフォルダのルートで `import_confluence.py` を実行します

