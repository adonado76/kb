---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "admin"
title: "Lineage Search"
breadcrumb: []
source_path: "admin/lineage-search.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Lineage Search

Lineage search allows the user to search through the complex lineage graph for an entity matching
the search term.

![](../../resources/images/studio_images/filter-lineage.png)

Even on a relatively small lineage diagram like this, it can be difficult to, at a glance, tell
what all of the entities are. This is especially true for sub-types like columns or dimensions, that
are represented as icons rather than full-on boxes with names. This is where search comes in. For
example, typing in "unit" (the search is not case-sensitive) will highlight all entities that match
the search query:

![](../../resources/images/studio_images/filter-lineage-1.png)

And fade out entities that do not match the search query

![](../../resources/images/studio_images/filter-lineage-2.png)

Multiple search terms separated by a space are treated as an implicit OR, e.g. an entity will be
highlighted if it matches any of the search terms

![](../../resources/images/studio_images/multiple-search.png)

## Filter

In addition to highlighting entities that match the search queries, the results can also be used
to filter the graph down for subsequent requests. The three buttons to the right of the search bar
are used for this purpose :

- Add Matching
- Hide Non-matching
- Hide Matching

## Add Matching

Click the Add Matching (green plus) button

![](../../resources/images/studio_images/lsearch-5.png)

This will generate a new lineage diagram where all of the entities that previously matched the
search query have been added to the "Added Keys" section. While this might not have an immediately
obvious effect on the diagram, it does mean that these entities will persist on subsequent queries,
even if their overall subtype is hidden. This is very useful when you want to find a specific
entity, like a column or a dimension, that you want to trace lineage for, even if you are not
actually interested in that type of entity or wish to exclude them for readability.

![](../../resources/images/studio_images/lsearch-6.png)
![](../../resources/images/studio_images/lsearch-7.png)

## Hide Non-matching

To hide entities from the diagram that did not match the "Units FTE" query, select the Hide
Non-matching (red minus) icon.

![](../../resources/images/studio_images/lsearch-4.png)

A new lineage query is issued, where all of the entities that were previously faded out are now
effectively hidden from the diagram and all subsequent lineage queries

![](../../resources/images/studio_images/lsearch-3.png)

## Hide Matching

To hide entities from the diagram that matched the "Units FTE" query, select the rightmost
Hide Matching (green minus) icon

![](../../resources/images/studio_images/lsearch-2.png)

This will generate a new lineage diagram where all of the entities that previously matched the
search query have been added to the "Hidden Keys" section, effectively hiding them from the diagram
and all subsequent lineage queries. This can useful to quickly filter out spurious results or
branching paths that you are not interested in tracing:

![](../../resources/images/studio_images/lsearch-1.png)
