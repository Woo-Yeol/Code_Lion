### API Key 발급받기

**[참조]**

[[OpenWeatehrMap - API Key](https://www.notion.so/likelion/OpenWeatherMap-API-Key-12b608bcfd8840ccb53a2c16771f2648)]

#### 사용법

1. OpenWeather(OpenAPI) 사이트 방문하기

[[OpenWeather](https://home.openweathermap.org/users/sign_up)]

2. 가입 후 이메일 인증 완료하기

3. My API Keys를 확인한다.

### API 알아보기

* API(Application Programming Interface) : 응용 프로그램 / 프로그래밍 / 인터페이스
    * 프로그램과 프로그램의 연결 시켜주는 역할 (Client - Server)

* 날씨를 알아보는 방법
    * 크롤링을 통한 정보 확인
    * 세계의 날씨를 서버에 저장하는 프로그램을 우리의 프로그램에 연결하여 조회하는 방법

#### API Key 알아보기

OpenAPI를 사용할 떄 방명록과 같은 존재이다.

### API 링크 만들기

```
city = "해당 도시 이름"
apikey = "개인 API Key"
api = "http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api}" # 도시이름과 API Key를 필요로 한다.
```

* f-string : 문자열에 문자를 삽입하기 위한 파이썬 문법
    * api = f"링크 + 중괄호를 품은 변수"
