---
title: Book (paging and other behavior variations)
id: 11
layout: recipe
tags: [image, text, layout]
summary: "These manifests use the 'behavior' property to specify how the canvases should be displayed in the viewer in relation to one another, such as paged for a book or continuous for a scroll."
---

## Use Cases

... inform a client of the appropriate presentation configuration and navigational cues for a variety of Canvas relationships. Some examples include book view layout for books imaged with one image per page, or if imaged with one image per 2-page spread; images that can be stitched together in the viewer for a continuous view, such as a scroll imaged in multiple shots; or individual items such as inserts, foldouts, etc. This recipe provides examples for three different use cases:

Use case 1: A book object that has the concept of recto and verso,  with one image per page that is best presented in book view, with two facing pages displaying next to one another.

Use case 2: A scroll object

Use case 3: I have a book object... shot two up -OR- manuscript fragments from a single manuscript (I have objects that are photographed in different ways (one image per page, one image per pair of open pages, etc).)

## Implementation notes

The `behavior` property tells a presentation client one part of how to display a sequence of resources to a viewer.

The property is permissible for all resource types, but some values (`unordered`, `individuals`, `continuous`, `paged`) are permissible only for `Collection`, `Manifest`, and `Range`, while others (`facing-pages`, `non-paged`) are permissible only on `Canvas`. Clients should process the property on any resource type.

The default `behavior` value, if not specified, is `individuals` for Layout Behaviors (as opposed to Temporal, Collection, Range, and Miscellaneous Behaviors).

In addition to `behavior`, you may want to use the `viewingDirection` property (see also [Book (paging variations)][0010] recipe), for example `right-to-left` or `top-to-bottom`, depending on the expected user experience for viewing your resource(s) or the specificities of the physical object and its digital surrogate. Interactions between `viewingDirection` and `behavior`, especially when they are set on multiple and/or hierarchical resources, need special attention. You are recommended to read [the Presentation 3.0 spec on `behavior`](https://iiif.io/api/presentation/3.0/#behavior) carefully and to keep current with future releases.

## Restrictions

None known

## Example 1: `behavior` `paged`

This manifest shows the playbill for "Akiba gongen kaisen-banashi," "Futatsu chōchō kuruwa nikki", and "Godairiki koi no fūjime", kabuki performances at the Chikugo Theater in Osaka from the fifth month of Kaei 2 (May, 1849).

[JSON-LD](manifest-paged.json)
[View in Universal Viewer](https://universalviewer.io/examples/#?manifest={{ site.url }}{{ site.baseurl }}{{ page.url }}manifest-paged.json)

{: .line-numbers data-download-link data-download-link-label="Download me" data-line="15" data-src="manifest-paged.json" }
```json
```

## Example 2: `behavior` `continuous`

This manifest represents an Ethiopian scroll, written in Gez for Walata Eyasus (secular name Berenash), that contains prayers to guard against epilepsy and for the binding of demons. Its full length is 2.245m and is roughly .11m wide over its length.

Note that as of the writing of this recipe, the `behavior` value of `continuous` has no noticeable effect in the Universal Viewer demonstration linked below. However, for forward compatibility it is a part of the manifest.

[JSON-LD](manifest-continuous.json)
[View in Universal Viewer](https://universalviewer.io/examples/#?manifest={{ site.url }}{{ site.baseurl }}{{ page.url }}manifest-continuous.json)

{: .line-numbers data-download-link data-download-link-label="Download me" data-line="15-18" data-src="manifest-continuous.json" }
```json
```
## Example 3: `behavior` `individuals`

This manifest represents an Ethiopian scroll, written in Gez for Walata Eyasus (secular name Berenash), that contains prayers to guard against epilepsy and for the binding of demons. Its full length is 2.245m and is roughly .11m wide over its length.

Note that as of the writing of this recipe, the `behavior` value of `continuous` has no noticeable effect in the Universal Viewer demonstration linked below. However, for forward compatibility it is a part of the manifest.

[JSON-LD](manifest-individuals.json)
[View in Universal Viewer](https://universalviewer.io/examples/#?manifest={{ site.url }}{{ site.baseurl }}{{ page.url }}manifest-individuals.json)

{: .line-numbers data-download-link data-download-link-label="Download me" data-line="15-18" data-src="manifest-individuals.json" }
```json
```

# Related recipes

* [Book (simplest)][0009]
* [Book (paging variations)][0011]
* [Thumbnails][0012]
* [Table of contents (ranges) - book chapters][0024]

{% include acronyms.md %}
{% include links.md %}