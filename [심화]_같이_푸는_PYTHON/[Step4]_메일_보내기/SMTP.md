### SMTP(Simple Mail Transfer Protocol)

#### SMTP란?
 - SMTP 형식을 통해서 우리가 원하는 곳으로 메일을 보낼 수 있다.
    - 클라이언트에서 서버로 / 서버에서 서버로 메일을 보낼 때 사용하는 Protocol
    - 서버에서 클라이언트로 정보를 가져올 때 IMAP 형식을 사용한다.

#### SMTP Server 주소 & 포트 (Address / Port)
 - Address : smtp.gmail.com
 - Port : 465 (GMAIL 지명 포트)

#### SMTPlib 사용하기
**SMTP 서버 사용하기**

import smtplib

1. SMTP 메일 서버를 연결한다.
    - smtp = smtplib.SMTP(SMTP_SERVER, SMTP_PORT)
    - SSL 암호화 방식을 처리 : smtp = smtplib.SMTP_SSL(SMTP_SERVER,SMTP_PORT)

2. SMTP 메일 서버에 로그인한다.
    - smtp.login("ID", "PW")

3. SMTP 메일 서버로 메일을 보낸다.
    - smtp.send_message("E-mail의 내용")

smtp.quit()

#### MIME
**전자우편을 위한 인터넷 표준 포맷**
- email.message 모듈 - .EmailMessage 기능

from email.message import EmailMessage

1. 이메일을 만든다.
    - EmailMessage()

2. 이메일에 내용을 담는다.
    - message.set_content("본문")

3. 발신자, 수신자를 설정한다. 
    - MIME의 header : Subject, From, To
    - message["Subject"] = "제목"
    - message["From"] = "발신자 이메일"
    - message["To"] = "수신자 이메일"
