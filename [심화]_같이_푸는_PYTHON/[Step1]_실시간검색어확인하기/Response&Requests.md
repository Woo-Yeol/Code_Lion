### 요청하고 응답받기 1
```
requests.get(url) : GET 요청을 보내는 기능
    return : requests.response
```

#### PUT, GET, POST, DELETE
 - client - Server : 요청과 응답의 관계
    - Server : 요청에 대한 응답을 하는 역할
    - Client : 요청을 받고 응답값을 다루는 역할

### 요청하고 응답받기 2
```
requests.get(url,params=None,**kwargs)
    Parameter : url, params, **kwargs
    Return : requests.Response
```

### 요청하고 응답받기 3

- 응답 객체 확인하기
```
import requests
url = "http://www.daum.net"
print(requests.get(url))
-------------------------------
# <Response [200]> 200은 성공을 뜻한다.
```

- 응답값 확인하기
```
import requests
url = "http://www.daum.net"
print(requests.get(url).text)
-------------------------------
# url의 html 내용
```

- 다양한 응답값에서 추출한 결과
```
response.url : url 주소
response.content : 
response.encoding : 해당 html 인코딩 형식
response.headers : 
response.json :
response.links :
response.ok : 응답값 응답 완료 여부
response.status_code : 응답값 상태에 대한 코드
```