entity-resolution
===================

This project aims to build an interactive entity resolution service based on both [Duke](http://code.google.com/p/duke) and [Elasticsearch](http://www.elasticsearch.org)... 

## Request
 ```
{
  "query": {
    "custom_score": {
      "query": {
        "match": {
          "name": "foo"
        }
      },
      "script": "identity-resolution",
      "lang": "native",
      "params": {
        "entity": [
            {
                "name" : "name",
                "cleaners" : ["asciifolding","lowercase"],
                "comparator" : "levensthein",
                "low" : 0.5,
                "high" : 0.95
            },
            {
                "name" : "surname",
                "cleaners" : ["asciifolding"],
                "comparator" : "levensthein",
                "low" : 0.5,
                "high" : 0.95
            }            
        ]
      }
    }
  }
}
```

## Licence 

This project is licended under LGPLv3
