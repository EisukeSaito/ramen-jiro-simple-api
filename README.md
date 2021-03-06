## What is this
This make a virtual REST API server on GitHub repository.
By analyzing JSON files, the script makes directories and some files.
User can access datas of JSON file as if REST API server

## Sample
Now shopinfo.json is in ./json and have following structure.

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
            "ramen_image_url": "https://spinning.jp/wp-content/uploads/2019/11/%E3%82%B7%E3%83%A3%E3%82%AB%E3%83%AA%E3%82%AD%E3%80%80%E9%86%A4%E6%B2%B9%E3%82%AA%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%80%80%E8%84%82%E3%80%81%E9%87%8E%E8%8F%9C%E3%80%81%E3%82%AC%E3%83%BC%E3%83%AA%E3%83%83%E3%82%AF%E5%A2%97%E3%81%97.png",
            "shop_image_url": "http://cdn-ak.f.st-hatena.com/images/fotolife/f/frnk/20130405/20130405181533.jpg",
            "tabelog_url": "https://tabelog.com/hokkaido/A0101/A010201/1041731/"
        },
        
        ・・・・・・
    ]
}
```

The script loads JSON files in ./json .

Now only 'shopinfo.json' is in ./json . When main.py runs and loads shopinfo.json, it makes files as you can access like following.

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
