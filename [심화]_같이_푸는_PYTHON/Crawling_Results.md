### 파일로 출력하기
- open(파일,모드) :
    - 모드 : 
        - r : read
        - w : write
        - a : append (새로운 값 추가하기)
```
...
search_rank_file = open("rankresult.txt","w")
...
for result in results:
    search_rank_file.write(str(rank)+"위:"+result.get_text()+"\n")
    print(rank,"위 : ",result.get_text(),"\n")
    rank += 1

# rankresult.txt 파일 생성 및 정보 업데이트
```

### 네이버 실시간 검색어 크롤링 하기
- 네이버는 로봇이 자동으로 크롤링하는 것을 방지한다.
    - headers = {'User-Agent':'Mozilla/5.0 (Windows NT 6.3; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/63.0.3239.132 Safari/537.36'}
    - 선언 후 requests.get(url, headers = headers)
    - headers를 포함하여 GET을 요청하여 로봇이 아님을 증명한다.

**Code**
```
from bs4 import BeautifulSoup
import requests
from datetime import datetime

headers = {'User-Agent':'Mozilla/5.0 (Windows NT 6.3; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/63.0.3239.132 Safari/537.36'}
url = "https://datalab.naver.com/keyword/realtimeList.naver?age=20s"
response = requests.get(url,headers=headers)
soup = BeautifulSoup(response.text, 'html.parser')
rank = 1
# span - item_title
results = soup.findAll('span','item_title')

print(response.text)

search_rank_file = open("rankresult.txt","a")

print(datetime.today().strftime("%Y년 %m월 %d일의 실시간 검색어 순위입니다.\n"))

for result in results:
    search_rank_file.write(str(rank)+"위:"+result.get_text()+"\n")
    print(rank,"위 : ",result.get_text(),"\n")
    rank += 1
```