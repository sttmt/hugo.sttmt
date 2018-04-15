---
title: "Search"
date: 2018-04-15T22:19:34+09:00
tags:
- search
draft: false
---

<div id="search-box">
    <!-- 検索ボックス用の空DOM -->
</div>

<ul id="hits">
    <!-- 検索結果用のDOM、各結果をliで置くためulにしている -->
</ul>

<div id="pagination">
    <!-- ページネーションがここに -->
</div>

<script>
 // instantSearchを初期化
var search = instantsearch({
  appId: 'TTY2CV8DU0',
  apiKey: '341d5a221ef93efd8688d4e332c32a8f',
  indexName: 'sttmt.netlify',
  urlSync: true
});

// 検索ボックスをDOMに設定
search.addWidget(
  instantsearch.widgets.searchBox({
	  container: '#search-box',
	  placeholder: 'Search for posts',
	  poweredBy: true
  })
);

// 検索結果をDOMに設定
// 結果には<li>を使うように
search.addWidget(
  instantsearch.widgets.hits({
	  container: '#hits',
	  templates: {
      empty: 'No results',
	    item: '<li><code>{{ dateString }}</code> <a href="{{permalink}}">{{ title }}</a></li>'
	  }
  })
);

// 検索結果をページネーションするための設定
search.addWidget(
  instantsearch.widgets.pagination({
	  container: '#pagination',
	  maxPages: 20,
	  scrollTo: false
  })
);

search.start();
</script>