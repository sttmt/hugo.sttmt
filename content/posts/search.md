---
title: Search
date: 2018-04-15 22:19:34 +0900
hidden: true
---
<div id="search-box">
<!-- SearchBox widget will appear -->
</div>

<ul id="hits">
<!-- Hits widget will appear here -->
</ul>

<div id="pagination">
<!-- Pagination widget will appear here -->
</div>

<script>
// initialize InstantSearch
var search = instantsearch({
appId: 'TTY2CV8DU0',
apiKey: '341d5a221ef93efd8688d4e332c32a8f',
indexName: 'sttmt.netlify',
urlSync: true
});

// initialize SearchBox
search.addWidget(
instantsearch.widgets.searchBox({
container: '#search-box',
placeholder: 'Search for posts',
poweredBy: true
})
);

// initialize hits widget
search.addWidget(
instantsearch.widgets.hits({
container: '#hits',
templates: {
empty: 'No results',
item: '<li><code>{{ dateString }}</code> <a href="{{permalink}}">{{ title }}</a></li>'
}
})
);

// initialize pagination
search.addWidget(
instantsearch.widgets.pagination({
container: '#pagination',
maxPages: 20,
scrollTo: false
})
);

search.start();
</script>
<script src="https://cdn.jsdelivr.net/npm/instantsearch.js@2.7.4"></script>
