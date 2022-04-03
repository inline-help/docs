## Inline Help API documentation

In the following the api to create Help Tips.

**base url**: https://api.inline.help/api/v1/

### Security

We will use JWT token from our SSO server:
- https://sso.inline.help


### How to create helptips
- method: POST 
- path: /helptips
- authorization: Bearer xxxxxx

Where xxxxxx is the access_token that you received after loign.


An help tip json object will be like this:

```json
{
    "code":"101",
    "lang":"it",
    "type":"XPATH",
    "direction":"UNDER",
    "position":"xxxx",
    "title":"title",
    "preview":"preview content",
    "body":"body content",
    "uri":"https://uri.to/use",
    "style":"minimal-theme",
    "icon":"fa-box",
    "project_uuid":"69959754-7e91-466e-a4b5-22e1fc8096f8",
    "tags":"a,b,c"
  }
```

### Parameters

- **code** - a client custom code
- **lang** - it's a project language (ie: it, en, de...)
- **type** - ABSOLUTE, CSS, XPATH
- **direction** - UNDER, BOTTOM, RIGHT, LEFT
- **position** - the absolute coordinate inside page
- **title** - help titp title
- **preview** - short text to show when the mouse go ahead of the icon
- **body** - long text to show opening the tip
- **uri** - uri page that will show the tips with same uri
- **style** - theme style for icons
- **project_uuid** - it's tips aggregator
- **tags** - can be usefull to aggregate tips by short name


### How to get helptips
- method: GET 
- path: /helptips
- authorization: Bearer xxxxxx

### Query parameters to paginate:
- startRow (default 0)
- pageSize (default 10)
- orderBy (default orderBy title asc)

### Query parameters to filtering:
- obj.uuid (to find a specific helptip by uuid) => equivalent to GET /helptips/{uuid}
- obj.project_uuid => by specific **project uuid**
- obj.code  => by specific **code**
- obj.lang => by specific **lang**
- like.tags => like as **tag**
- like.title => like as **title**

