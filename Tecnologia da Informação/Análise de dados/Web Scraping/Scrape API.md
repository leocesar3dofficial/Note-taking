# Scrape API

1. Find the request with the desired response data in Chrome Developer Tool Fetch/XHR.
2. Right-click on the request name > copy > Copy as cURL (bash).
    - Check the response Size and Time to find the request, it is normally the bigger and the one that took more time.
3. Postman > New collection > Import > Raw text > paste copied request > Continue > Import.
4. Test the request with the Send button, change parameters to find desired response.
5. Click on Code snippet > choose Python - Requests as the language library > copy code.
6. Paste it in an IDE file and work from there.

## Sample Code

```python
import requests
import pandas as pd

def get_json():
    url = "https://catalog.chaldal.com/searchOld"

    payload = """{
        "apiKey": "e964fc2d51064efa97e94db7c64bf3d044279d4ed0ad4bdd9dce89fecc9156f0",
        "storeId": 1,
        "warehouseId": 8,
        "pageSize": 8000,
        "currentPageIndex": 0,
        "metropolitanAreaId": 1,
        "query": "",
        "productVariantId": -1,
        "canSeeOutOfStock": "true",
        "filters": []
    }"""
    
    headers = {
        'authority': 'catalog.chaldal.com',
        'pragma': 'no-cache',
        'cache-control': 'no-cache',
        'sec-ch-ua': '"Chromium";v="92", " Not A;Brand";v="99", "Google Chrome";v="92"',
        'accept': 'application/json',
        'sec-ch-ua-mobile': '?0',
        'user-agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/92.0.4515.159 Safari/537.36',
        'content-type': 'application/json, application/json',
        'origin': 'https://chaldal.com',
        'sec-fetch-site': 'same-site',
        'sec-fetch-mode': 'cors',
        'sec-fetch-dest': 'empty',
        'referer': 'https://chaldal.com/',
        'accept-language': 'en-US,en;q=0.9'
    }

    response = requests.request("POST", url, headers=headers, data=payload)

    return response.json()  # parse text

def save_to_csv(data):
    if data:
        df = pd.json_normalize(data)
        df.to_csv("filename.csv")

def main():
    data = get_json()
    save_to_csv(data.get('hits'))
    print('Done')

if __name__ == '__main__':
    main()
```