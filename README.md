## What is this
This make a virtual REST API server on GitHub repository.
By analyzing JSON files, the script makes directories and some files.
User can access datas of JSON file as if REST API server

## Sample
Now sample.json is in ./json and have following structure.

```json

{
    "data": [
        {
            "no": "0",
            "name": "札幌店",
            "location": {
              "pref_code": "hokkaido",
              "pref_name": "北海道",
              "address": "北海道札幌市北区北六条西8-8-11"
            },
            "station": [
              "JR函館本線 さっぽろ",
              "JR千歳線 さっぽろ"
            ],
            "close_day": [
              "sunday",
              "holiday"
            ],
            "open_day": {
              "weekday": [
                "11:00～14:00",
                "17:00～21:00"
              ],
              "saturday": [
                "11:00～15:00"
              ]
            },
            
            ・・・・・・
}
```

The script loads JSON files in ./json .

Now only 'sample.json' is in ./json . When main.py runs and loads sample.json, it makes files as you can access like following.

|  data you want  |  REST API URL  |
| ---- | ---- |
|  all of shopinfo.json  |  https://eisukesaito.github.io/ramen-jiro-simple-api/shopinfo/  |
|  data[0] of shopinfo.json  | https://eisukesaito.github.io/ramen-jiro-simple-api/shopinfo/data/0  |
|  data[1] of shopinfo.json  |  https://eisukesaito.github.io/ramen-jiro-simple-api/shopinfo/data/1  |
|  data[1]['no'] of shopinfo.json  |  https://eisukesaito.github.io/ramen-jiro-simple-api/shopinfo/data/1/no  |

## Usage
1. Fork this repo
2. Activate GitHub Actions and Pages (gh-pages)
3. Set JSON files in ./json
4. Push to master and fire Actions, then start hosting.
