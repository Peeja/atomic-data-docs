{{#title Atomic Data Collections - Filtering, Sorting & Querying}}
# Atomic Collections

_URL: [https://atomicdata.dev/classes/Collection](https://atomicdata.dev/classes/Collection)_

Sooner or later, developers will have to deal with (long) lists of items.
For example, a set of blog posts, activities or users.
These lists often need to be paginated, sorted, and filtered.
For dealing with these problems, we have Atomic Collections.

An Atomic Collection is a Resource that links to a set of resources.
Note that Collections are designed to be _dynamic resources_, often (partially) generated at runtime.
Collections are [Endpoints](../endpoints.md), which means that part of their properties are calculated server-side.
Collections have various filters (`subject`, `property`, `value`) that can help to build a useful query.

- `members`: How many items (members) are visible per page.
- `subject`: Filter results by a property URL.
- `property`: Filter results by a property URL.
- `value`: Filter results by a Value.
- `sort_by`: A property URL by which to sort.
- `sort_desc`: Sort descending, instead of ascending. Defaults to `false`.
- `current_page`: The number of the current page.
- `page_size`: How many items (members) are visible per page.
- `total_pages`: How many pages there are for the current collection.
- `total_items`: How many items (members) are visible per page.
<!-- - `scope`: The parent resource in which to limit the query (see Atomic Hierarchy) -->

## Persisting Properties vs Query Parameters

Since Atomic Collections are dynamic resources, you can pass query parameters to it.
The keys of the query params match the shortnames of the properties of the Collection.

For example, let's take the [Properties Collection on atomicdata.dev](https://atomicdata.dev/collections/property).
We could limit the page size to 2 by adding the `page_size=2` query parameter: `https://atomicdata.dev/collections/property?page_size=2`.
Or we could sort the list by the description property: `https://atomicdata.dev/collections/property?sort_by=https%3A%2F%2Fatomicdata.dev%2Fproperties%2Fdescription`.
Note that URLs need to be URL encoded.

These properties of Collections can either be set by passing query parameters, or they can be _persisted_ by the Collection creator / editor.
