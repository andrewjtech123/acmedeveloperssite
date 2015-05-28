---
title: HangIt Developer API Objects
permalink: /HangIt_Developer_API_Objects/
tags: intro
audience: developer, marketer
keywords:
last_updated:
summary:
---

# HangIt Developer API Objects

Using the HangIt Developer API, you have access to the following objects to manage location setup functions.

* Campaign
* Event
* Place
* Schedule
* Media

## Campaign

Campaigns are organizational containers for Events.  They enable marketers and advertisers to manage multiple events under the umbrella of a Campaign, to better orchestrate their efforts.

| Name     | Type | Description  |
| :------- | ----: | ----:
| `cid` |       int   |  campaign id.  **Campaign id must be valid and belong to the user's account.** |
|    |       |
|     |

## Events

Events are the main units of the HangIt location setup.  Events can be grouped by Campaigns and include the following sub-objects: places, schedule, media.

The following table describes the event metadata.

| Name     | Type | Description  |
| :------- | ----: | -------:
| `eventname` | string   |  Name of the event. |
|   `type` |     integer  | There are 3 event types:   `Target - Entry`, `Target - Exit` , `Intercept`  See definition below.  Possible values: 1, 2, 3
||
|
|  `alerttext`  |  string   | Text that will display as part of the event alert. |
|   `tags` |     string  | Tags to categorize the event.  |
|  `startdate`  |  Date   | Start date for the event. eg. 01/01/2015 |
|   `enddate` |     Date  | End date for the event eg. 12/31/2015  |
|  `private`, `public` | string | Events can be private or public.  For more information, see below.


### Event Types

As described in the table above there are three event types:

* *Target - Entry:* This is a defined target zone that will trigger a notification/message upon entering the area
* *Target - Exit:* This is a defined target zone that will trigger a notification/message upon exiting an area.
* *Intercept:* This is a defined target zone that will trigger a notification/message upon entering and then link to a second Target zone.

### Private and Public Events

* Private: Events are presented to devices that have downloaded the application by which the event was configured
* Public: Events that are available for other applications to consume and present to their audience.


## Places

Places are a sub-object of Events.  They describe the geographical location where the event will be made available over the course of the event lifespan.

The following table describes the Places sub-object.

| Name     | Type | Description  |
| :------- | ----: | -------:
| `name` | string   |  Place name. |
|   `lat` |integer  | latitude for the event. eg. 26.5|
|  `lng`  |  integer   | longitude for the event. eg. -81.6 |
|   `radius` |     integer  | radius comprising the event. eg. 20  |
|  `color`  |  Date   | RBG color that will show up for the bounding box on the map. eg. #1E90FF | |
| |

## Schedule

Scedule is a sub-object of Events.  The Schedule object indicates the daily hours that the event will run for.  The schedule parameters are defined in the table below.

| Name     | Type | Description  |
| :------- | ----: | -------:
| `sun` , `mon`, `tues` etc. | string   |  Specific day of the week. |
|   `hours` |integer  | Hours during the day when the event campaign will run.  For example to run from 1-12 on `sun` input 9, 10, 11, 12.|
|  

## Media

Media is a sub-object of Events.  Media indicates the media type and url to the media, as described in the table below.

| Name     | Type | Description  |
| :------- | ----: | -------:
| `media type` | string   |  Indicates type of media to be served. TODO indicate media types |
|   `url` |url  | URL to the media location. eg. "http://hub.tappinn.com/blog/wp-content/uploads/2013/12/Mobile_Coupon_QRCode.jpg"|
|  






> Written with [StackEdit](https://stackedit.io/).
