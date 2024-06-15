# Requests and Beautiful Soup

## Install
```bash
pip install requests
pip install beautifulsoup4
```

## Import
```python
import requests
from bs4 import BeautifulSoup
```

## Extract
```python
url = # paste URL from target site
headers = # get from Insomnia or Postman
request = requests.get(url, headers)
print(request.status_code) # see if the request worked: other than 200 is bad
soup = BeautifulSoup(request.content, 'html.parser')
soup.prettify() # properly indent HTML content, only necessary for visualization
```

## Transform
```python
divs = soup.find_all('div', class_='class_name')

for item in divs:
    title = item.find('a').text.strip()
    company = item.find('span', class_='company').text.strip()

    try:
        salary = item.find('span', class_='salary').text.strip()
    except:
        salary = ''

    summary = item.find('span', {'class': 'summary'}).text.strip()

    job = {
        'title': title,
        'company': company,
        'salary': salary,
        'summary': summary
    }
```
