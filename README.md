# Streamlike Looker Studio Connector

See [Looker Studio](https://developers.google.com/looker-studio)

This Connector retrieves data from your Streamlike account.

What do you need ?

- A Streamlike API token generated with analytics, media, playlists, tags, keywords reading rights.
- That's all

## 1. Endpoints

Here is the list of the endpoints currently available

### 1. analytics/catalogs

Returns catalog duration per company.

- Parameters

| Name                 | Description                                                                                               |
|----------------------|-----------------------------------------------------------------------------------------------------------|
| Aggregation          | Aggregation mode  : <br/>	{choice values: ["total"]}                                                     |
| Company fields       | Company info displayed <br/>{choice values: ["name","logo_url","parent.id","parent.name"] multiple: true} |
| Company Id           | Array of company_id to apply filter                                                                       |
| Include subsidiaries | Boolean                                                                                                   |

- Fields

| Name                       | Type     | Description                      |
|----------------------------|----------|----------------------------------|
| Company Id                 | Text     |                                  |
| Company Name               | Text     | If company field name set        |
| Date                       | Date     |                                  |
| Duration Archived          | Duration |                                  |
| Duration high availability | Duration |                                  |
| Duration total             | Duration |                                  |
| Logo Image                 | Image    | If company field logo_url  set   |
| Logo Url                   | URL      | If company field logo_url set    |
| Parent Id                  | Text     | If company field parent.id set   | 
| Parent Name                | Text     | If company field parent.name set | 

### 2. analytics/playbacks

Returns playback count per company and per type.

- Parameters

| Name                 | Description                                                                                               |
|----------------------|-----------------------------------------------------------------------------------------------------------|
| Aggregation          | Aggregation mode  : <br/>	{choice values: ["total"]}                                                     |
| Company fields       | Company info displayed <br/>{choice values: ["name","logo_url","parent.id","parent.name"] multiple: true} |
| Company Id           | Array of company_id to apply filter                                                                       |
| Include subsidiaries | Boolean                                                                                                   |
| Keywords Ids         |                                                                                                           |
| Media Id             |                                                                                                           |
| Playlist Ids         |                                                                                                           |
| Source               | {choice values: ["streamlike","youtube","dailymotion"]}                                                   |
| Tag Ids              |                                                                                                           |
| User Token           |                                                                                                           |

- Fields

| Name              | Type   | Description                      |
|-------------------|--------|----------------------------------|
| Company Id        | Text   |                                  |
| Company Name      | Text   | If company field name set        |
| Daylimotion views | Number |                                  |
| Date              | Date   |                                  |
| Logo Image        | Image  | If company field logo_url  set   |
| Logo Url          | URL    | If company field logo_url set    |
| Parent Id         | Text   | If company field parent.id set   | 
| Parent Name       | Text   | If company field parent.name set |
| Streamlike views  | Number |                                  |
| Total views       | Number |                                  |
| Youtube views     | Number |                                  |

### 3. analytics/transfer

Returns bandwidth consumption data per company.

- Parameters

| Name                 | Description                                                                                               |
|----------------------|-----------------------------------------------------------------------------------------------------------|
| Aggregation          | Aggregation mod  : <br/>	{choice values: ["total"]}                                                       |
| Company fields       | Company info displayed <br/>{choice values: ["name","logo_url","parent.id","parent.name"] multiple: true} |
| Company Id           | Array of company_id to apply filter                                                                       |
| Include subsidiaries | Boolean                                                                                                   |
| Keywords Ids         |                                                                                                           |
| Media Id             |                                                                                                           |
| Playlist Ids         |                                                                                                           |
| Tag Ids              |                                                                                                           |

- Fields

| Name         | Type   | Description                                                     |
|--------------|--------|-----------------------------------------------------------------|
| Company Id   | Text   | If Aggregation is set to none                                   |
| Company Name | Text   | If Aggregation is set to none and company field name set        |
| Date         | Date   |                                                                 |
| Live         | Number | Live bandwidth,                                                 |
| Logo Image   | Image  | If Aggregation is set to none and company field logo_url set    |
| Logo Url     | URL    | If Aggregation is set to none and company field logo_url set    |
| Other        | URL    | VOD bandwidth,                                                  |
| Parent Id    | Text   | If Aggregation is set to none and company field parent.id set   | 
| Parent Name  | Text   | If Aggregation is set to none and company field parent.name set |
| Total        | Number | Total Bandwidth                                                 |
| VOD          | Number | VOD bandwidth, If Aggregation is not total                      |

### 4. analytics/playback/top/popular

Returns Streamlike playbacks top.

- Parameters

| Name                 | Description                                                                                                                                                                                                           |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Company id           | Array of company_id to apply filter                                                                                                                                                                                   |
| Include subsidiaries | Boolean                                                                                                                                                                                                               |
| Keywords Ids         |                                                                                                                                                                                                                       |
| Max result           |                                                                                                                                                                                                                       |
| Media fields         | Media Info displayed<br/>  {choice values: [<br/>"name","permalink",<br/>"cover.files.cover","cover.files.thumbnail","cover.files.large","cover.files.extralarge",<br/>"source.duration","type"<br/>] multiple: true} |
| Media Id             |                                                                                                                                                                                                                       |
| Playlist Ids         |                                                                                                                                                                                                                       |
| Tag Ids              |                                                                                                                                                                                                                       |
| User token           |                                                                                                                                                                                                                       |

- Fields

| Name                 | Type   | Description |
|----------------------|--------|-------------|
| Cover                | Text   |             |
| Media Id             | Text   |             |
| Player               | URL    |             |
| Name                 | Text   |             |
| Permalink            | Text   |             |
| Playbacks            | Number |             |
| Source duration      | Number |             |
| Thumbnail            | Text   |             |
| Thumbnail large      | Text   |             |
| Thumbnail extralarge | Text   |             |
| Type                 | Text   |             |

### 5. analytics/greenhousegas

Returns Streamlike playbacks top.

- Parameters

| Name                 | Description                                                                                               |
|----------------------|-----------------------------------------------------------------------------------------------------------|
| Aggregation          | Aggregation mod  : <br/>	{choice values: ["total"]}                                                       |
| Company fields       | Company info displayed <br/>{choice values: ["name","logo_url","parent.id","parent.name"] multiple: true} |
| Company Id           | Array of company_id to apply filter                                                                       |
| Include subsidiaries | Boolean                                                                                                   |

- Fields

| Name         | Type   | Description                                                     |
|--------------|--------|-----------------------------------------------------------------|
| Company Id   | Text   | If Aggregation is set to none                                   |
| Company Name | Text   | If Aggregation is set to none and company field name set        |
| Date         | Date   |                                                                 |
| GHG DEV      | URL    |                                                                 |
| GHG Infra    | URL    |                                                                 |
| GHG Net      | URL    |                                                                 |
| GHG Total    | URL    |                                                                 |
| Logo Image   | Image  | If Aggregation is set to none and company field logo_url set    |
| Logo Url     | URL    | If Aggregation is set to none and company field logo_url set    |
| Parent Id    | Text   | If Aggregation is set to none and company field parent.id set   | 
| Parent Name  | Text   | If Aggregation is set to none and company field parent.name set |

### 6. analytics/company/stats

- Fields

| Name                  | Type   | Description |
|-----------------------|--------|-------------|
| Medias audio count    | Number |             |
| Medias total duration | Number |             |
| Medias video count    | Number |             |
| Users count           | Number |             |

### 7. analytics/company/activity

| Name                   | Type   | Description |
|------------------------|--------|-------------|
| Catalog total duration | Number |             |
| Encoding count         | Number |             |
| Encoding duration      | Number |             |
| Period                 | Text   |             |
| Playbacks count        | Number |             |

### 8. analytics/company/billable

| Name                               | Type   | Description |
|------------------------------------|--------|-------------|
| Catalog archived duration          | Number |             |
| Catalog high availability duration | Number |             |
| Catalog total duration             | Number |             |
| Date                               | Text   |             |
| Greenhouse gas                     | Number |             |
| Transfer                           | Number |             |
