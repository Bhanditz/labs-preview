---
layout: api-page
title: API Change Log
---

This document describes the changes of Europeana API. The changes are grouped by new API versions. We deploy new versions of the portal and the API quite regularly, but not all new versions has change in the interface. The API documentation always describes the current version of the API. We don't have (yet?) however API call to get the actual version, so the API users should see the date of changes.

## Version 2.0.6 (2013-08-09)

New allowable value for the _profile_ parameter: `params`. When client adds `params` to the _profile_ parameter, the header of the response will contain a `params` key, which lists the requested and default parameters of the API call. The client can use profile _profile_ parameter in search and object calls. The parameter accepts both single and multiple values separated by comma or space (such as `&profile=standard` or `&profile=standard,params` or `&amp;profile=standard%20params`).

### Example

```
http://europeana.eu/api/v2/search.json?wskey=xxxxxxxx&amp;query=mona+lisa&amp;profile=standard%20params
```

returns

<pre>
{
  "apikey": "xxxxxxxxx",
  "action": "search.json",
  "success": true,
  "requestNumber": 6,
  "params": {
    "query": "mona lisa",
    "profile": "standard params",
    "start": 1,
    "rows": 12
  },
  "itemsCount": 12,
  "totalResults": 195,
  "items": [...]
}
</pre>

## Version 2.0.8 (2013-10-23)

New parameter: `reusability`. It might have two possible values: Free and Limited. It is an additional filter, which selects those items, which can be reusable free, or in a limited way. They are shorthands for a couple of right values:

Free:

* NOC: http://creativecommons.org/publicdomain/mark/
* CC-ZERO: http://creativecommons.org/publicdomain/zero/1.0/*
* CC-BY: http://creativecommons.org/licenses/by/
* CC-BY-SA: http://creativecommons.org/licenses/by-sa/

Limited

* CC-BY-NC: http://creativecommons.org/licenses/by-nc/
* CC-BY-NC-SA: http://creativecommons.org/licenses/by-nc-sa/
* CC-BY-NC-ND: http://creativecommons.org/licenses/by-nc-nd/
* CC-BY-ND: http://creativecommons.org/licenses/by-nd/
* OOC-NC: http://www.europeana.eu/rights/out-of-copyright-non-commercial/

It has double effects 1) it filter the search result with the appropriate right values, 2) if facets are requested, it provides a new facet, called REUSABILITY.

Example:

```
http://localhost:8080/api/v2/search.json?wskey=api2demo&query=*:*&reusability=free&qf=TYPE:VIDEO&profile=portal
```

returns

```JavaScript
{
  "apikey": "xxxxxxxxxx",  
  "action": "search.json",  
  ...
  "items": [ … ],  
  ...
  "facets": [
    ...
    {  
      "name": "REUSABILITY",
      "fields": [
        {"label": "Limited", "count": 9795},
        {"label": "Free", "count": 3659}
      ]
    }
  ]
}
```

