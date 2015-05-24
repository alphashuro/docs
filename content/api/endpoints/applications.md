## Applications

* [List user applications](#list-user-applications)
* [Get an application](#get-an-application)
* [List builds](#list-builds)
* [List deploys](#list-deploys)

### <a name="list-user-applications"></a>List user applications

List all applications owned by the user or organization. This will only contain
application that the authenticated user has access to. If the call is made
without a token, only public applications will be returned.

***
`GET /api/v3/applications/:username`
***

#### Response

```
Status: 200 OK
```

```json
[
  {
    "stack": 5,
    "privacy": "public",
    "createdAt": "2015-01-28T17:04:09.851Z",
    "owner": {
      "meta": {
        "werckerEmployee": false,
        "username": "wercker"
      },
      "userId": "55310d295732ce8a41000054",
      "avatar": {
        "gravatar": "33a5bfbcf8a2b90f40e849b6f1fa5eeb"
      },
      "name": "wercker",
      "type": "wercker"
    },
    "name": "docs",
    "url": "https://app.wercker.com/api/v3/applications/wercker/docs",
    "id": "54c9168980c7075225004157"
  }
]
```

### <a name="get-an-application"></a>Get an application

Get the details of a single application.

***
`GET /api/v3/applications/:username/:application`
***

#### Response

```
Status: 200 OK
```

```json
{
  "stack": 5,
  "privacy": "public",
  "id": "54c9168980c7075225004157",
  "url": "https://app.wercker.com/api/v3/applications/wercker/docs",
  "name": "docs",
  "owner": {
    "meta": {
      "werckerEmployee": false,
      "username": "wercker"
    },
    "userId": "55310d295732ce8a41000054",
    "avatar": {
      "gravatar": "33a5bfbcf8a2b90f40e849b6f1fa5eeb"
    },
    "name": "wercker",
    "type": "wercker"
  },
  "builds": "https://app.wercker.com/api/v3/applications/wercker/docs/builds",
  "deploys": "https://app.wercker.com/api/v3/applications/wercker/docs/deploys",
  "scm": {
    "repository": "docs",
    "owner": "wercker",
    "type": "git"
  },
  "createdAt": "2015-01-28T17:04:09.851Z"
}
```

### <a name="list-builds"></a>List builds

Retrieve all builds of an application.

***
`GET /api/v3/applications/:username/:application/builds`
***

#### Response

```
Status: 200 OK
```

```json
[
  {
    "status": "finished",
    "startedAt": "2015-04-30T17:06:04.686Z",
    "id": "554260f7dc16db44791955a7",
    "url": "https://app.wercker.com/api/v3/builds/554260f7dc16db44791955a7",
    "branch": "hide_api",
    "createdAt": "2015-04-30T17:05:59.209Z",
    "finishedAt": "2015-04-30T17:09:02.753Z",
    "message": "Hide API header",
    "progress": 100,
    "result": "passed"
  }
]
```

### <a name="list-deploys"></a>List deploys

Retrieve all deploys of an application.

***
`GET /api/v3/applications/:username/:application/deploys`
***

#### Response

```
Status: 200 OK
```

```json
[
  {
    "progress": 100,
    "createdAt": "2015-05-02T21:26:18.834Z",
    "result": "passed",
    "status": "finished",
    "url": "https://app.wercker.com/api/v3/deploys/554540fadc16db447926a82a",
    "id": "554540fadc16db447926a82a"
  }
]
```