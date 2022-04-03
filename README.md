## Inline Help API documents

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


## languages

It depends from the project options, normally: en, it...

## type values
- ABSOLUTE
- CSS
- XPATH

## direction values
- UNDER
- BOTTOM
- RIGHT
- LEFT
