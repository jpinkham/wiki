# Firefox storage locations

## places.sqlite

Purpose: Holds bookmarks, URLs visited, files downloaded, etc

### Interesting tables

The field lists are not exhaustive, see the full schema for that info. These are just fields I want to look into further

* moz_bookmarks
  * id (int): primary key, used to tie bookmarks to other tables for additional data
  * type (int):  not sure yet what this ties to
  * fk (int): this is a foreign key for another table, not sure which one yet
  * parent (int): assuming this represents parent/child for folders
  * position (int): assuming this indicates menu vs toolbar and who knows what else
  * title (text): display name
  * guid (text): ??

* moz_bookmarks_deleted -- guess your bookmarks are never truly deleted
  * guid: guess this is an FK for moz_bookmarks.guid
  * dateRemoved

* moz_historyvisits
  * place_id: FK for places.id

* moz_inputhistory -- no idea
  * place_id (int): FK for moz_places.id?
  * input (text): text you entered somewhere on site?

* moz_origins -- no idea
  * 

* moz_places
  * id (int): primary key
  * url
  * visit_count
  * frecency:  frequency of visiting site.  yes, it is spelled incorrectly for whatever reason.
  * last_visit_date
  * hidden: ??
  * typed: ??

### DB schema
<!-- markdownlint-disable-next-line -->
<details>
    <!-- markdownlint-disable-next-line -->
    <summary>Click to expand/collapse</summary>

```sql
sqlite> .schema
CREATE TABLE moz_origins ( id INTEGER PRIMARY KEY, prefix TEXT NOT NULL, host TEXT NOT NULL, frecency INTEGER NOT NULL, UNIQUE (prefix, host) );
CREATE TABLE moz_places (   id INTEGER PRIMARY KEY, url LONGVARCHAR, title LONGVARCHAR, rev_host LONGVARCHAR, visit_count INTEGER DEFAULT 0, hidden INTEGER DEFAULT 0 NOT NULL, typed INTEGER DEFAULT 0 NOT NULL, frecency INTEGER DEFAULT -1 NOT NULL, last_visit_date INTEGER , guid TEXT, foreign_count INTEGER DEFAULT 0 NOT NULL, url_hash INTEGER DEFAULT 0 NOT NULL , description TEXT, preview_image_url TEXT, origin_id INTEGER REFERENCES moz_origins(id));
CREATE INDEX moz_places_url_hashindex ON moz_places (url_hash);
CREATE INDEX moz_places_hostindex ON moz_places (rev_host);
CREATE INDEX moz_places_visitcount ON moz_places (visit_count);
CREATE INDEX moz_places_frecencyindex ON moz_places (frecency);
CREATE INDEX moz_places_lastvisitdateindex ON moz_places (last_visit_date);
CREATE UNIQUE INDEX moz_places_guid_uniqueindex ON moz_places (guid);
CREATE INDEX moz_places_originidindex ON moz_places (origin_id);
CREATE TABLE moz_historyvisits (  id INTEGER PRIMARY KEY, from_visit INTEGER, place_id INTEGER, visit_date INTEGER, visit_type INTEGER, session INTEGER);
CREATE INDEX moz_historyvisits_placedateindex ON moz_historyvisits (place_id, visit_date);
CREATE INDEX moz_historyvisits_fromindex ON moz_historyvisits (from_visit);
CREATE INDEX moz_historyvisits_dateindex ON moz_historyvisits (visit_date);
CREATE TABLE moz_inputhistory (  place_id INTEGER NOT NULL, input LONGVARCHAR NOT NULL, use_count INTEGER, PRIMARY KEY (place_id, input));
CREATE TABLE moz_bookmarks (  id INTEGER PRIMARY KEY, type INTEGER, fk INTEGER DEFAULT NULL, parent INTEGER, position INTEGER, title LONGVARCHAR, keyword_id INTEGER, folder_type TEXT, dateAdded INTEGER, lastModified INTEGER, guid TEXT, syncStatus INTEGER NOT NULL DEFAULT 0, syncChangeCounter INTEGER NOT NULL DEFAULT 1);
CREATE TABLE moz_bookmarks_deleted (  guid TEXT PRIMARY KEY, dateRemoved INTEGER NOT NULL DEFAULT 0);
CREATE INDEX moz_bookmarks_itemindex ON moz_bookmarks (fk, type);
CREATE INDEX moz_bookmarks_parentindex ON moz_bookmarks (parent, position);
CREATE INDEX moz_bookmarks_itemlastmodifiedindex ON moz_bookmarks (fk, lastModified);
CREATE INDEX moz_bookmarks_dateaddedindex ON moz_bookmarks (dateAdded);
CREATE UNIQUE INDEX moz_bookmarks_guid_uniqueindex ON moz_bookmarks (guid);
CREATE TABLE moz_keywords (  id INTEGER PRIMARY KEY AUTOINCREMENT, keyword TEXT UNIQUE, place_id INTEGER, post_data TEXT);
CREATE TABLE sqlite_sequence(name,seq);
CREATE UNIQUE INDEX moz_keywords_placepostdata_uniqueindex ON moz_keywords (place_id, post_data);
CREATE TABLE moz_anno_attributes (  id INTEGER PRIMARY KEY, name VARCHAR(32) UNIQUE NOT NULL);
CREATE TABLE moz_annos (  id INTEGER PRIMARY KEY, place_id INTEGER NOT NULL, anno_attribute_id INTEGER, content LONGVARCHAR, flags INTEGER DEFAULT 0, expiration INTEGER DEFAULT 0, type INTEGER DEFAULT 0, dateAdded INTEGER DEFAULT 0, lastModified INTEGER DEFAULT 0);
CREATE UNIQUE INDEX moz_annos_placeattributeindex ON moz_annos (place_id, anno_attribute_id);
CREATE TABLE moz_items_annos (  id INTEGER PRIMARY KEY, item_id INTEGER NOT NULL, anno_attribute_id INTEGER, content LONGVARCHAR, flags INTEGER DEFAULT 0, expiration INTEGER DEFAULT 0, type INTEGER DEFAULT 0, dateAdded INTEGER DEFAULT 0, lastModified INTEGER DEFAULT 0);
CREATE UNIQUE INDEX moz_items_annos_itemattributeindex ON moz_items_annos (item_id, anno_attribute_id);
CREATE TABLE moz_meta (key TEXT PRIMARY KEY, value NOT NULL) WITHOUT ROWID ;
CREATE TABLE sqlite_stat1(tbl,idx,stat);
```

</details>
