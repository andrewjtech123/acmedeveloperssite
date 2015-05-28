---
title: HangIt Developer API Reference
permalink: /HangIt_Developer_API_Reference/
tags: intro
audience: developer, marketer
keywords:
last_updated:
summary:
---

# POST /v1/events/create

## Definition

Using `apikey`, `secret` and a valid JSON payload creates an Event with Places, Schedule and optional media.

## Attributes

For a definition of all method attributes see Objects.

## Request Format

```
Type: POST url: /v1/event/create
JSON Example
        {
            "auth": {
                "apikey": "d5d53d6e8b9a4a6c66bbebd64aa53d12",
                "secret": "f0b0da17f86d6c1af86a0bbc838d1282"
            },
            "campaign": {
                "cid": 12
            },
            "events": [{
                "eventname": "A CO",
                "type": 3,
                "alerttext": "a co Message",
                "tags": "tag1,tag2",
                "startdate": "01/01/2015",
                "enddate": "12/31/2015",
                "public":1,
                "places": [{
                    "name": "office",
                    "lat": 26.5,
                    "lng": -81.6,
                    "radius": 20,
                    "color": "#1E90FF"
                },
                {
                    "name": "home",
                    "lat": 26.8,
                    "lng": -81.9,
                    "radius": 10,
                    "color": "#32CD32"
                }],
                "schedule": [{
                    "sun": {
                        "hours": "9,10,11,12"
                    },
                    "mon": {
                        "hours": "24"
                    },
                    "tue": {
                        "hours": "24"
                    },
                    "wed": {
                        "hours": "24"
                    },
                    "thu": {
                        "hours": "24"
                    },
                    "fri": {
                        "hours": "24"
                    },
                    "sat": {
                        "hours": "24"
                    }
                }]
        },
        {
            "eventname": "B Co",
            "type": 3,
            "alerttext": "b co Message",
            "tags": "tag1,tag2",
            "startdate": "01/01/2015",
            "enddate": "12/31/2015",
            "public":0,
                "places": [{
                    "name": "office",
                    "lat": 25.1,
                    "lng": -82.3,
                    "radius": 20,
                    "color":"#32CD32"
                },
                {
                    "name": "home",
                    "lat": 25.6,
                    "lng": -82.8,
                    "radius": 10,
                    "color":"#1E90FF"
                }],
                "schedule": [{
                    "sun": {
                        "hours": "8,9,10"
                    },
                    "mon": {
                        "hours": "24"
                    },
                    "tue": {
                        "hours": "24"
                    },
                    "wed": {
                        "hours": "24"
                    },
                    "thu": {
                        "hours": "24"
                    },
                    "fri": {
                        "hours": "24"
                    },
                    "sat": {
                        "hours": "24"
                    }
                }]
            }],
            "media": {
                "type": 1,
                "url": "http://hub.tappinn.com/blog/wp-content/uploads/2013/12/Mobile_Coupon_QRCode.jpg"
            }
        }
```

## Response Format

### Success

```
{
"status":"ok",
"message":"",
"eventid": 123456
}
```

###Failure

A detailed response message will be sent if validation fails.
```
{
"status":"notok",
"message":"not a valid ..."
}
```


>
> Written with [StackEdit](https://stackedit.io/).<!--se_discussion_list:{"ZNh4m00PrN87AayLzfn78sf9":{"selectionStart":218,"selectionEnd":222,"commentList":[{"content":"link"}],"discussionIndex":"ZNh4m00PrN87AayLzfn78sf9"}}-->
