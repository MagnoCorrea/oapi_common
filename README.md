# OGC API (OAPI) Common Specification

[OGC](http://opengeospatial.org) API standards define modular API building blocks to spatially enable Web APIs. The OGC API family of standards is organized by resource type. Each resource has an associated API standard. These resource-specific API standards share a common core. This OGC API Common standard specifies requirements which are shared by all OGC API standards. The OGC API Common standard is maintained on this GitHub repository.

## Overview

A Web Feature Service is a standard API that represents collections of geospatial data.

```
GET /
```



```
GET /api
```

```
GET /collections
```

Lists the collections of data on the server that can be queried ([7.11](https://rawcdn.githack.com/opengeospatial/WFS_FES/3.0.0-draft.1/docs/17-069.html#_feature_collections)), and each describes basic information about the resource, like its id and description, as well as the spatial and temporal extents of all the data contained

```
GET /collections/{collectionId}/items?bbox=160.6,-55.95,-170,-25.89
```

Requests all the data in the collection identified by the "collectionId" that is in the New Zealand economic zone. 

Possible response formats are specific to a resource type, but typically HTML and [GeoJSON]((http://geojson.org/) are supported. The format selected for the response is determined using [HTTP content negotiation](https://restfulapi.net/content-negotiation/).

Data is returned in pageable chunks, with each response containing a `next` link
as many collections are quite large. The core specification supports a few basic filters, in
addition to the `bbox` filter above, with extensions providing more advanced options.
([7.13](https://rawcdn.githack.com/opengeospatial/WFS_FES/3.0.0-draft.1/docs/17-069.html#_feature_collection))
```
GET /collections/{collectionId}/items/{featureId}
```

Returns a single 'feature' - something in the real-world (a building,
a stream, a county, etc.) that typically is described by a geometry plus other properties.
This provides a stable, canonical URL to link to the 'thing'.

## Using the standard

A stable draft is available. Note that the draft uses the title "Web Feature Service" or "WFS",
version 3.0. This was the original title and newer editor's drafts already use the title
"OGC API - Features".

* [OGC API - Features - Part 1: Core, First Draft Release](https://rawcdn.githack.com/opengeospatial/WFS_FES/3.0.0-draft.1/docs/17-069.html)

A [PDF version](https://portal.opengeospatial.org/files/?artifact_id=79027&version=1) is available, too.

Those who want to just see the endpoints and responses can explore the generic
OpenAPI definition on SwaggerHub:

* [OGC API Features 1.0.0-draft.1 openapi.yaml](https://app.swaggerhub.com/apis/cholmesgeo/WFS3/M1)

Several implementations of the draft standard exist:

* [Implementations of the draft specification / demo services](implementations.md)

## Communication

Join the [mailing list](https://lists.opengeospatial.org/mailman/listinfo/wfs-fes.swg) or [![chat at https://gitter.im/opengeospatial/WFS_FES](https://badges.gitter.im/opengeospatial/WFS_FES.svg)](https://gitter.im/opengeospatial/WFS_FES?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Most all work on the specification takes place in [GitHub issues](https://github.com/opengeospatial/WFS_FES/issues),
so browse there to get a good idea of what is happening, as well as past decisions.

## Additional Information

* [Checklist for implementers](guide/conformance_checklist.md)

Also a non-normative document, the "Users Guide", is being developed.

In addition to feedback from the initial implementations as well as discussions on GitHub and in the OGC/ISO working group,
the current draft standard has been tested in a [WFS 3.0 Hackathon](http://www.opengeospatial.org/blog/2764), the [OGC Testbed-14](http://www.opengeospatial.org/projects/initiatives/testbed14), the [OGC Vector Tiles Pilot](https://www.opengeospatial.org/projects/initiatives/vt-pilot-2018) and other activities.

Feedback for the Core is collected and discussed in the
[GitHub issues for Part 1, Core](https://github.com/opengeospatial/WFS_FES/issues?q=is%3Aissue+is%3Aopen+label%3A%22Document%3A+Part+1+-+Core%22). The current expectation is to have a stable version of the Core specification by August 2019. This version would
then be the input for the next steps in the standardization process in OGC and ISO/TC 211.

* [Background of this activity](background.md)
* [The next version of WFS - an overview](overview.md)
* [OGC API - Features - Part 1: Core, Editor's Draft](http://docs.opengeospatial.org/DRAFTS/17-069.html), also available as
[PDF](http://docs.opengeospatial.org/DRAFTS/17-069.pdf)

## Contributing

The contributor understands that any contributions, if accepted by the OGC Membership and ISO/TC 211, shall be incorporated into OGC and ISO/TC 211 Web Feature Service standards documents and that all copyright and intellectual property shall be vested to the OGC.

The WFS/FES Standards Working Group (SWG) is the group at OGC responsible for the stewardship of the standard, but is working to do as much work in public as possible.

* [Open issues](https://github.com/opengeospatial/WFS_FES/issues)
* [Proposing changes](https://github.com/opengeospatial/WFS_FES/wiki/Propose-a-change-to-a-draft-of-a-WFS-specification-document)
* [Copy of License Language](https://raw.githubusercontent.com/opengeospatial/WFS_FES/master/LICENSE)
```
