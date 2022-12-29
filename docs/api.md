# 9Hits API

---------

9Hits API allows you to access and manage some resources from the 9Hits Panel. You can get your API key from your [profile page](https://panel.9hits.com/user/profile).

## Get profile
Return your profile information.
```
GET https://panel.9hits.com/api/profileGet?key=YOUR_API_KEY
```
??? abstract "Sample Response"
    ``` js
    {
        "status": "ok",
        "messages": null,
        "data": {
            "username": "daniel",
            "email": "daniel@9hits.com",
            "joined": "2015-02-21 15:32:44",
            "token": "1a8cb897ca8b97c897c98a7cbd880123",
            "funds": 38.288,
            "slots": {
                "used": 5,
                "available": 78
            },
            "points": 803.57,
            "membership": "VIP",
            "membershipEndDate": "2021-01-31 22:03:27"
        }
    }
    ```

## Get custom user-agents
Return all your custom user-agent group.
```
GET https://panel.9hits.com/api/uaGet?key=YOUR_API_KEY
```

??? abstract "Sample Response"
    ``` js
    {
        "status": "ok",
        "messages": [
            "Fetched 2"
        ],
        "data": [
            {
                "id": 743,
                "title": "My Customize Firefox"
            },
            {
                "id": 2467,
                "title": "iPhone6"
            }
        ]
    }
    ```

## Get campaigns
Return your campaigns.
```
GET https://panel.9hits.com/api/siteGet?key=YOUR_API_KEY[&page=1&limit=100&filter=condition]
```

??? abstract "Sample Request"
    ```
    Get your first 100 campaign:
    GET https://panel.9hits.com/api/siteGet?key=YOUR_API_KEY

    Get your first 500 campaign:
    GET https://panel.9hits.com/api/siteGet?key=YOUR_API_KEY&limit=500&page=1

    Get all your campaigns filtered by title or url:
    GET https://panel.9hits.com/api/siteGet?key=YOUR_API_KEY&filter=my%20site
    GET https://panel.9hits.com/api/siteGet?key=YOUR_API_KEY&filter=my-site.com

    Get a single campaign by id:
    GET https://panel.9hits.com/api/siteGet?key=YOUR_API_KEY&filter=id:812031
    ```

??? abstract "Sample Response"
    ``` js
    {
        "status": "ok",
        "messages": [
            "Fetched 1"
        ],
        "data": [
            {
                "id": 812031,
                "title": "My Site",
                "isAdult": false,
                "hasCoinMining": false,
                "urls": [
                    "https://my-site.com"
                ],
                "referrers": {
                    "mode": "basic",
                    "urls": [
                        "https://www.facebook.com",
                        "https://www.google.com",
                    ]
                },
                "duration": [
                    59,
                    70
                ],
                "platforms": {
                    "mobile": 50,
                    "desktop": 48,
                    "custom": 2,
                    "custom-ua": [
                        {
                            "id": "743",
                            "rate": 30
                        },
                        {
                            "id": "8523",
                            "rate": 70
                        }
                    ]
                },
                "macros": "await WaitForLoading();\r\nwhile(true)\r\n{\r\n    await Delay(Random(5000, 15000));\r\n    await ClickRandomLink();\r\n}",
                "popupMacros": "await WaitForLoading();\r\nwhile(true)\r\n{\r\n    await Delay(Random(5000, 15000));\r\n    await ClickRandomLink();\r\n}",
                "connectionTypes": [
                    "system",
                    "http",
                    "socks4",
                    "socks5",
                    "ssh"
                ],
                "connectionSpeed": "slow+",
                "performance": "slow+",
                "geo": {
                    "rule": "all",
                    "by": "country",
                    "codes": null
                },
                "acceptLanguages": null,
                "capping": {
                    "type": "own",
                    "value": 0,
                    "shared": 0
                },
                "maxHits": 0,
                "untilDate": "2021/10/13 06:08:04",
                "estimatedHits": 123456,
                "confirmedHits": 123000,
                "maxPopups": 3,
                "fingerprintSpoof": true,
                "allowProxy": true,
                "allowIPv6": true,
                "allowBlockedPopups": true,
                'ipFilter': {
                    'type': "0",
                    'rules': "1.55.*,223.54.1.*,2001:2f:*"
                },
                "hourlyLimit": {
                    "speed": "fast",
                    "hours": [
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        },
                        {
                            "min": 0,
                            "max": 0
                        }
                    ]
                },
                "disJsRate": 0,
                "disImageRate": 0,
                "disCookieRate": 100,
                "cpuUsage": 0.57,
                "forceHide": true,
                "adSafe": "google-ads",
                "webSecurity": false,
                "alexaEnabled": true,
                "userState": "running",
                "systemState": "approved"
            }
        ]
    }
    ```

!!! warning
    The `limit` is 100 by default, maximum is 500, the `page` starts from 1. The returns are sorted by creation date.

## Add new campaign
The request body contains your campaign information in JSON format.
```
POST https://panel.9hits.com/api/siteAdd?key=YOUR_API_KEY
```

??? abstract "Sample Request (Simple)"
    ``` js
    {
        "title": "My Site",
        "isAdult": false,
        "hasCoinMining": false,
        "urls": [
            "http://my-site.com/about.html"
        ],
        "duration": [
            22,
            70
        ]
    }
    ```

??? abstract "Sample Request (Full)"
    ``` js
    {
        "title": "My Site",
        "isAdult": false,
        "hasCoinMining": false,
        "urls": [
            "http://my-site.com/about.html",
            "http://my-site.com/pricing.html"
        ],
        "referrers": {
            "mode": "advanced", //basic
            "urls": [           //if mode is basic, urls should be array ["http://url1", "http://url2"]
                {
                    "url": "https://www.fb.com",
                    "rate": 70
                },
                {
                    "url": "https://www.twitter.com",
                    "rate": 30
                }
            ]
        },
        "duration": [
            22, //from
            70  //to
        ],
        "platforms": {
            "mobile": 32,
            "desktop": 66,
            "custom": 2,
            "custom-ua": [
                {
                    "id": "743",
                    "rate": 30
                },
                {
                    "id": "8523",
                    "rate": 70
                }
            ] //array of user-agent group id wite usage rate
        },
        "macros": "await WaitForLoading();\r\nwhile(true)\r\n{\r\n    await Delay(Random(5000, 15000));\r\n    await ClickRandomLink();\r\n}",
        "popupMacros": "await WaitForLoading();\r\nwhile(true)\r\n{\r\n    await Delay(Random(5000, 15000));\r\n    await ClickRandomLink();\r\n}",
        "connectionTypes": [
            "system",
            "http",
            "socks4",
            "socks5",
            "ssh"
        ],
        "connectionSpeed": "medium+", //slow+, good+
        "performance": "medium+", //slow+, good+
        "geo": {
            "rule": "all", //any, except
            "by": "country", //continent
            "codes": ["US", "VN"]
        },
        "acceptLanguages": null, //["VN", "US"]
        "capping": {
            "type": "shared",   //own
            "value": 86400,     //in seconds
            "shared": 324153    //if type is shared, here is the master campaign id
        },
        "maxHits": 110,
        "untilDate": "2021/10/13 06:08:04",
        "maxPopups": 3,
        "fingerprintSpoof": true,
        "allowProxy": false,
        "allowIPv6": false,
        "allowBlockedPopups": false,
        'ipFilter': {
            'type': "0", //0: by session ip, 1: by machine ip, 2: by all
            'rules': "1.55.*,223.54.1.*,2001:2f:*"
        },
        "hourlyLimit": {
            "speed": "fast", //slow
            "hours": [ //Array with 24 elements corresponds to 24 hours from 00 to 23
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 10,
                    "max": 10
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                },
                {
                    "min": 0,
                    "max": 0
                }
            ]
        },
        "disJsRate": 0,
        "disImageRate": 0,
        "disCookieRate": 100,
        "forceHide": true,
        "adSafe": "google-ads", //can be empty
        "webSecurity": false,
        "userState": "running" //paused
    }
    ```


??? abstract "Sample Response"
    ``` js
    {
        "status": "ok",
        "messages": [
            "Created #400466"
        ],
        "data": null
    }
    ```

## Update a campaign
The request body contains your campaign information in JSON format, just similar to the request body of the `Add Campaign API`, but you need to add the `campaign id`, you don't need to submit all campaign information, just specify the information you need to update. You can also submit resetHitCounter (optional) as true to reset hit counter.

```
POST https://panel.9hits.com/api/siteUpdate?key=YOUR_API_KEY
```

??? abstract "Sample Request"
    ``` js
    {
        "id": 400466,
        "title": "My New Site",
        "resetHitCounter": true,
        "urls": [
            "http://my-site.com/new-post1.html",
            "http://my-site.com/new-post2.html"
        ],
        ...
    }
    ```

??? abstract "Sample Response"
    ``` js
    {
        "status": "ok",
        "messages": [
            "Updated #400466"
        ],
        "data": null
    }
    ```

## Delete campaigns
Delete your campaigns by id
```
POST https://panel.9hits.com/api/siteDel?key=YOUR_API_KEY
```

??? abstract "Sample Request"
    ``` js
    [400466, 400467, 400468]
    ```

??? abstract "Sample Response"
    ``` js
    {
        "status": "ok",
        "messages": null,
        "data": null
    }
    ```

## Session stats
Get your session stats

```
GET https://panel.9hits.com/api/sessionStats?key=YOUR_API_KEY
```

??? abstract "Sample Response"
    ``` js
    {
        "status": "ok",
        "messages": null,
        "data": {
            "total": 1,
            "online": 1,
            "system": 1,
            "http": 0,
            "socks4": 0,
            "socks5": 0,
            "ssh": 0,
            "isProxy": 0
        }
    }
    ```

## Transfer points
Transfer points from your account to an other member
```
POST https://panel.9hits.com/api/transfer?key=YOUR_API_KEY
```

??? abstract "Sample Request"
    ``` js
    {
        "receiver" : "daniel",
        "message" : "Hi, a small gift for you ;)",
        "amount" : 100
    }
    ```

??? abstract "Sample Response"
    ``` js
    {
        "status": "ok",
        "messages": [
            "You have sent 90 points to daniel"
        ],
        "data": {
            "sender": "john",
            "receiver": "daniel",
            "amount": 100,
            "net": 90,
            "fee": 10
        }
    }
    ```

## Transfer funds
Transfer funds from your account to an other member. **This function is for reseller only**.
```
POST https://panel.9hits.com/api/fund?key=YOUR_API_KEY
```

??? abstract "Sample Request"
    ``` js
    {
        "receiver" : "daniel",
        "message" : "Thank you",
        "amount" : 100
    }
    ```

??? abstract "Sample Response"
    ``` js
    {
        "status": "ok",
        "messages": [
            "You have sent $100 to daniel"
        ],
        "data": {
            "sender": "john",
            "receiver": "daniel",
            "amount": 100,
            "commission": 15
        }
    }
    ```

!!! tip
    Want more functions? Feel free to [make a request](https://feedback.userreport.com/0aa1e5ad-9e2d-4556-bc9d-36024ec04a0e/#ideas/popular)!