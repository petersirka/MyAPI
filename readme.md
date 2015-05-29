[![MIT License][license-image]][license-url]
# MyAPI 1.01

- easy tool for creating a rich documentation
- designed for REST services, libraries or frameworks
- single file without any dependencies
- __hashtags__ URL navigation
- JSON structure (you can edit JSON documentation in e.g. <https://itunes.apple.com/us/app/power-json-editor/id499768540?mt=12>)
- works on localhost without server
- based on <https://docs.totaljs.com>
- best use with [total.js - web application framework for node.js](https://www.totaljs.com)
- supports only IE9+, Chrome, Firefox and Opera
- simple support for mobile devices

## How do you use it?

Download `api.html` file and change the JSON content on the bottom page. You can change everything on the API page (localization, icons, etc.).

## How do you version it?

Rename the `api.html` by yourself, e.g. `api_v1.html`.

__Structure:__

```json
{
  "name": "My API name", // an API name
  "modified": "2015-12-12 12:00:00",
  "version": "1.0.0", // current version
  "build": "", // build version
  "default": "pages~Welcome", // a default page

  // API  
  "api":
  [
    {
        "group": "Group", // Menu caption (you can create multipe groups)
        "name": "Group name", // Item name in the menu
        "description": "Markdown (GFM) __syntax highlighting__." // optional
        "types": // all types / functionality
        [
            // REST EXAMPLE
            {
                "name": "Users: list of users",
                "description": "Markdown (GFM) __syntax highlighting__.",
                "method": "GET", // (optional) only for REST methods
                "output": "{\"success\":true}", // (optional) a response for the request
                "url": "http://blablabla.com/users/", // optional
                "return": "JSON", // (optional) a return value
                "headers": // (optional) only for REST
                [
                    "Content-Type: application/json",
                    "X-Token: 24953f1f8df2f84b8fe1"
                ]
                "params":
                [
                    {
                        "name": "search", // funcionallity (method, property, etc.) name
                        "type": "String", // method type
                        "description": "Search phrase (markdown is not supported)", // description
                        "options": ["optional"] // (optional) custom options
                    },
                    {
                        "name": "page",
                        "type": "Number",
                        "description": "Listing.",
                        "options": ["!important"] // !phrase is highlighted to red
                    },
                    {
                        "name": "page",
                        "type": "Number",
                        "description": "Listing."
                    }                    
                ]
            },

            // CLASSIC METHOD EXAMPLE (e.g. JavaScript)
            {
                "name": "Library.read()",
                "description": "Markdown (GFM) __syntax highlighting__.",
                "return": "String", // (optional) a return value
                "params":
                [
                    {
                        "name": "type",
                        "type": "Number",
                        "description": "Description ...",
                        "options": ["optional"] // (optional) custom options
                    }                 
                ]
            }            
        ]
    }
  ],
  // Pages (optional)
  "pages":
  [
    {
      "name": "Welcome",
      "body": "Markdown (GFM) __syntax highlighting__."
    },
    {
      "name": "Contact",
      "body": "Markdown (GFM) __syntax highlighting__."
    }    
  ],
  // Links (optional)
  "links":
  [
    {
      "name": "Homepage",
      "url": "http://www.totaljs.com"
    },
    {
      "name": "GitHub",
      "url": "https://github.com/petersirka/MyAPI"
    }    
  ]
}
```

## Contact

Peter Širka - <petersirka@gmail.com>

[license-image]: https://img.shields.io/badge/license-MIT-blue.svg?style=flat
[license-url]: license.txt
