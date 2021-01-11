### BeautifulSoap 1
- import 하고 사용하기
```
from bs4 import BeautifulSoup
...
print(type(response.text))
print(type(BeautifulSoup(response.text, 'html.parser')))

# <class 'str'>
# <class 'bs4.BeautifulSoap'>
```

### BeautifulSoap 2

 - BeautifulSoap(데이터, 파싱방법)
    - 데이터 : html or xml
    - Parsing(파싱) : 우리의 문서를 의미있는 값으로 변환
        - html.parser : 파이썬 기본 제공 Parser
```
...
    soup = BeautifulSoap(response.text, 'html.parser')
    print(soup.title)
    print(soup.title.string)
    print(soup.span)
    print(soup.findAll('span))

    # <title>Daum</title>
    # Daum
    # [가장 첫번째 span 태그]
    # [모든 span 태그]
```

### BeautifulSoap 3
**파일 출력**
```
file = open("daum.html","w")
file.write(response.text)
file.close()
```

**html 문서에서 모든 a태그를 가져오는 코드**
```
...
results = soup.findAll("a","link_favorsch"
print(results)

# [실시간 검색어 출력]
```

**예쁘게 출력하기**
```
from bs4 import BeautifulSoup
import requests
from datetime import datetime

url = "http://www.daum.net/"
response = requests.get(url)
soup = BeautifulSoup(response.text, 'html.parser')
rank = 1

results = soup.findAll('a','link_favorsch')

print(datetime.today().strftime("%Y년 %m월 %d일의 실시간 검색어 순위입니다. \n"))

for result in results:
    print(rank,"위 : ",result.get_text(),"\n")
    rank += 1
```

**결과 값**
```
20XX년 XX월 XX일의 실시간 검색어 순위입니다.

1 위 :  코로나19 발생현황

2 위 :  손흥민 1위

3 위 :  모니터추천

4 위 :  달이뜨는강 해명

5 위 :  업소용주방용품

6 위 :  사회적 거리두기

7 위 :  KBS 공식입장

8 위 :  우드슬랩식탁

9 위 :  유인나 MC발탁

10 위 :  전동지게차가격
```
