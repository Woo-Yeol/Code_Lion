### GoogleTrans 알아보기

#### GoogleTrans 란?

* 언어 감지 및 번역의 기능을 가지는 **Library**

* 언어 감지 : 해당 언어가 어떤 언어인지를 판별
* 언어 번역 : 언어를 다른 언어로 해석

```
from googletrans import Translator
```

#### 언어 감지하기

1. 번역기를 만든다.
    - Translator() : 번역기 제작

2. 언어 감지를 원하는 문장을 설정한다.
    - sentence = "문자열"

3. 언어를 감지한다.
    - detected = translator.detect(sentence)
    - Detected(lang = '언어', confidence='정확도')
    - detected.lang : 감지한 언어 값


**Code**

```
from googletrans import Translator

translator = Translator()

sentence = input("문장을 입력해주세요 : ")

detected = translator.detect(sentence)
```

#### 번역하기 1

1. 번역기를 만든다.
    - Translator() : 번역기 제작

2. 번역을 원하는 문장을 설정한다.
     
3. 번역을 원하는 언어를 설정한다.
    - 다양한 언어들 표기 :
        - 프랑스어 : fr
        - 아랍어 : ar
        - 베트남어 : vi
        - 스페인어 : es
        - 독일어 : de
        - 몽골어 : mn
        - 중국어 : zh-CN
        - 힌디어 : hi

4. 번역한다.
    - translate(text,dest,src) : 
        - text : 번역을 원하는 문장
        - dest : 목적지 언어(번역할 언어) (document에서 확인 가능)
        - src : text의 언어 (생략 가능 - 언어 감지 기능을 통한 생략)
    - Translated(src=[text의 언어], dest=[목적지 언어], text=[번역된 Text], pronounciation=[영어로 표기된 발음], extra_data=[부수적 데이터])

**Code**
```
from googletrans import Translator

translator = Translator()

sentence = input("문장을 입력해주세요 : ")
dest = input("어떤 언어로 번역해드릴까요? : ")

result = translator.translate(sentence,dest)

print("===========출 력 결 과===========")
print(detected.lang,":",sentence)
print(result.dest,":",result.text)
print("=================================")
```