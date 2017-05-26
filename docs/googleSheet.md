# Google sheet

Google sheet è una delle fonti con cui è possibile alimentare Simili Exhibit e quindi Petrusino.

## Come accedere ai dati

Da scrivere ...

## Come puntare a dati di un foglio elettronico multi sheet

Nel caso di fogli multipli l'URL per puntare allo sheet non è di immediata costruzione.

Il punto di partenza teorico è questo: [sheet API](https://developers.google.com/sheets/api/v3/worksheets).

Ecco un esempio pratico.

A partire da uno [spreadsheet di esempio](https://docs.google.com/spreadsheets/d/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984) composto da due foglie, si copia l'ID del foglio. Che in questo caso è `1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984`.

Si fa allora una chiamata con questo URL di base:

    https://spreadsheets.google.com/feeds/worksheets/YOUR_SPREADSHEET_ID/private/full

Si visualizza in vista codice:

    view-source:https://spreadsheets.google.com/feeds/worksheets/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/private/full

Si ottiene qualcosa come:

```XML
xmlns='http://www.w3.org/2005/Atom' xmlns:openSearch='http://a9.com/-/spec/opensearchrss/1.0/' xmlns:gs='http://schemas.google.com/spreadsheets/2006'><id>https://spreadsheets.google.com/feeds/worksheets/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/private/full</id><updated>2017-03-20T07:44:40.586Z</updated><category scheme='http://schemas.google.com/spreadsheets/2006' term='http://schemas.google.com/spreadsheets/2006#worksheet'/><title type='text'>sheet2json</title><link rel='alternate' type='application/atom+xml' href='https://docs.google.com/spreadsheets/d/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/edit'/><link rel='http://schemas.google.com/g/2005#feed' type='application/atom+xml' href='https://spreadsheets.google.com/feeds/worksheets/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/private/full'/><link rel='http://schemas.google.com/g/2005#post' type='application/atom+xml' href='https://spreadsheets.google.com/feeds/worksheets/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/private/full'/><link rel='self' type='application/atom+xml' href='https://spreadsheets.google.com/feeds/worksheets/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/private/full'/><author><name>tizio</name><email>tizio@gmail.com</email></author><openSearch:totalResults>2</openSearch:totalResults><openSearch:startIndex>1</openSearch:startIndex><entry><id>https://spreadsheets.google.com/feeds/worksheets/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/private/full/od6</id><updated>2017-03-20T07:44:40.586Z</updated><category scheme='http://schemas.google.com/spreadsheets/2006' term='http://schemas.google.com/spreadsheets/2006#worksheet'/><title type='text'>Sheet1</title><content type='text'>Sheet1</content><link rel='http://schemas.google.com/spreadsheets/2006#listfeed' type='application/atom+xml' href='https://spreadsheets.google.com/feeds/list/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/od6/private/full'/><link rel='http://schemas.google.com/spreadsheets/2006#cellsfeed' type='application/atom+xml' href='https://spreadsheets.google.com/feeds/cells/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/od6/private/full'/><link rel='http://schemas.google.com/visualization/2008#visualizationApi' type='application/atom+xml' href='https://docs.google.com/spreadsheets/d/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/gviz/tq?gid=0'/><link rel='http://schemas.google.com/spreadsheets/2006#exportcsv' type='text/csv' href='https://docs.google.com/spreadsheets/d/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/export?gid=0&amp;format=csv'/><link rel='self' type='application/atom+xml' href='https://spreadsheets.google.com/feeds/worksheets/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/private/full/od6'/><link rel='edit' type='application/atom+xml' href='https://spreadsheets.google.com/feeds/worksheets/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/private/full/od6/-u3c64m'/><gs:colCount>26</gs:colCount><gs:rowCount>1000</gs:rowCount></entry><entry><id>https://spreadsheets.google.com/feeds/worksheets/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/private/full/oyl1tnj</id><updated>2017-03-20T07:44:40.586Z</updated><category scheme='http://schemas.google.com/spreadsheets/2006' term='http://schemas.google.com/spreadsheets/2006#worksheet'/><title type='text'>Sheet2</title><content type='text'>Sheet2</content><link rel='http://schemas.google.com/spreadsheets/2006#listfeed' type='application/atom+xml' href='https://spreadsheets.google.com/feeds/list/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/oyl1tnj/private/full'/><link rel='http://schemas.google.com/spreadsheets/2006#cellsfeed' type='application/atom+xml' href='https://spreadsheets.google.com/feeds/cells/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/oyl1tnj/private/full'/><link rel='http://schemas.google.com/visualization/2008#visualizationApi' type='application/atom+xml' href='https://docs.google.com/spreadsheets/d/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/gviz/tq?gid=2091206789'/><link rel='http://schemas.google.com/spreadsheets/2006#exportcsv' type='text/csv' href='https://docs.google.com/spreadsheets/d/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/export?gid=2091206789&amp;format=csv'/><link rel='self' type='application/atom+xml' href='https://spreadsheets.google.com/feeds/worksheets/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/private/full/oyl1tnj'/><link rel='edit' type='application/atom+xml' href='https://spreadsheets.google.com/feeds/worksheets/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/private/full/oyl1tnj/-u3c64l'/><gs:colCount>26</gs:colCount><gs:rowCount>1000</gs:rowCount></entry></feed>
```


In questo codice i dettagli dei due fogli che compongono lo sheet di esempio, tra cui l'identificativo del secondo foglio, che in questo caso è `oyl1tnj`:

    https://spreadsheets.google.com/feeds/worksheets/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/private/full/oyl1tnj

Estratto l'id del foglio, l'URL per exhibit sarà

    https://spreadsheets.google.com/feeds/list/1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984/oyl1tnj/public/basic?hl=en_US&alt=json-in-script

Nota:

- `1m45f7Acta5HJyl3-wor0UlqW8-yKl3oE9pHQieGM984` è l'ID del google sheet;
- `oyl1tnj` è l'id del foglio di nostro interesse, tra i due che compongono il lo sheet.
