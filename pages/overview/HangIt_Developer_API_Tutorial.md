---
title: HangIt Developer API Tutorial
permalink: /HangIt_Developer_API_Tutorial/
tags: intro
audience: developer, marketer
keywords:
last_updated:
summary:
---

# Tutorial Introduction

The HangIt API is organized around REST.  Our API is designed to have predictable, resource-oriented URLs and to use HTTP response codes to indicate API errors.   JSON will be returned in all responses from the API, including errors.

The API endpoint is https://service.hangit.com


## Authentication

To create a new HangIt application and get an App ID and Secret token used to communicate with the API, visit our [developer portal](http://portal.hangit.com/newevent).


## Latest Version

The latest version of the Hangit API 1.0.0 and was released April, 2th 2015.

## Workflow

In order to use the HangIt Events API,  you must have registered your app with the HangIt portal and obtained  the `apikey` and `secret` token.  You must also have a valid campaign id, which will be used to groups events.  For more information, visit the [HangIt portal](http://portal.hangit.com).  

To send a valid API request

* Send a HTTP Post to the Hangit endpoint with /v1/events/create appened to the base url.  The HTTP Post must include a valid JSON payload, as per the example.

### Example

```json
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

```
Provided that the API request is properly formatted, the HangIt service will create a new Event record with corresponding Places and Schedules.  The service will return the new `event id` when a valid post has completed.


> Written with [StackEdit](https://stackedit.io/)
> .
