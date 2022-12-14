# Cypher-Studying
암호학 학습 내용 정리입니다.
```
01. 암호의 발전사
암호문(cipher text): 비밀을 유지하기 위해 당사자만 알 수 있도록 꾸민 기호.
 

암호 <->평문: 암호문과 반대되는 말로 누구나 알 수 있게 쓴 일반적인 글.

평문 -> 암호문 : 암호화(encryption) / 암호문 -> 평문 : 복호화(decryption) / 암호화 키 : 약속한 규칙.

암호화 알고리즘(encryption algorithm) : 암호화나 복호화를 수행할 때 양쪽이 알고 있어야 할 수단

 

1. 최초의 암호
최초의 암호는 기원전 480년 스파르타에서 추방되어 페르시아에서 살던 데마라토스가 페르시아 침략 계획을 나무판에 조각하고 밀랍을 발라 스파르타에 보낸 것이라 한다. 실제로 전달하려는 정보 자체를 숨기는 것을

스테가노그래피(stegano/graphy)라고 하는데, 이는 '덮다'라는 뜻의 그리스어와 '쓰다'라는 뜻이 합쳐진 말이다.

암호화 방식 - 전치 법 / 대체법

2. 전치법
: (transposition) 단순히 메시지에 들어 있는 문자 위치를 바꾸는 방법. ex) 'apple'을 두 글자씩 앞뒤로 섞어 'palpe'

 

3. 대체법
: (substitution) 메시지의 글자를 다른 글자로 대체하여 암호화하는 방법.

 + 단일 치환(monoalphabetic substitution) 시저, 모노 알파 베틱

   : 알파벳 한 글자`

   -시저 암호화

    알파벳 26자리를 3칸이나 4칸씩 오른쪽으로 이동하며 암호화하는 것.

   -모노 알파 베틱

    알파벳 26자리를 각각 다른 알파벳에 대응시킴으로써 26! 개의 암호문이 나온다

 

 + 다중 치환(polygram substitution) 비즈네르, 플레이페어

   : 암호화 키와의 매핑에 따라 알파벳 하나가 여러 가지 다른 알파벳으로 대체되어 암호화되는 것.

     ex) a가 c도 될 수 있고 r도 될 수 있음

    -비즈네르 암호화 https://ko.wikipedia.org/wiki/%EB%B9%84%EC%A6%88%EB%84%A4%EB%A5%B4_%EC%95%94%ED%98%B8 참고

     26 * 26의 알파벳 대칭 표를 이용하여 암호화하고자 하는 평문과 암호화 키를 매핑하고 암호화와 복호화를 수행하는       방식.

   

    -플레이페어 암호화

     비즈네르보다 발전된 형태로 2개로 이루어진 문자 쌍을 다른 문자 쌍으로 대체하는 암호화 방법.

https://en.wikipedia.org/wiki/Playfair_cipher 참고

 

02. 대칭 암호화 방식
- 더욱 강한 암호화를  위해선 혼돈(confusion)과 확산(diffusion) 성질을 이용한다

혼돈은 암호문의 통계적 성질과 평문의 통계적 성질의 관계를 난해하게 만드는 것.

 ->단일 대칭 암호화는 이러한 성질이 부족해 통계적 분석을 손쉽게 복호화가 가능

확산은 각각의 평문 비트와 키 비트가 암호문의 모든 비트에 영향을 주는 성질.

 

1. DES 알고리즘
:(Data Encryption Standard) 미국 NBS(National Bureau of Sandards)가 정보 보호를 목적으로 공모한 암호화 알고리즘.

 -64비트의 블록 암호화 알고리즘으로 56비트 크기의 암호화 키로 암호화한다. 따라서 생성 가능한 암호화 키는

2에 56승(7200조) 개다. 하나의 블록인 64의 비트를 L1(32비트)과 R1(32비트)로 나눈 뒤, R1을 암호화 키로 생성한

S-Box를 통해 f함수를 만들어서 치환하여 이 값을 L1과 논리합 하고, L2와 R2의 위치를 바꾸는 두 가지 기본 변환을 통해 암호화된다.



-라운드: 암호화 과정 한 단계로 혼돈은 이 라운드 과정에서 이루어진다.

하나의 블록에 대해 이러한 과정을 열여섯 번 수행하므로 16라운드 알고리즘이다.

S-Box : http://wiki.hash.kr/index.php/%EC%97%90%EC%8A%A4%EB%B0%95%EC%8A%A4 참조

 

2. 트리플 DES 알고리즘
: DES 복호화가 가능해짐에 따라 강화한 버전으로 2개의 암호화 키를 이용한다.

 

평문                ->                         1차 암호문            ->          2차 암호문      ->       마지막 암호문

 첫 번째 암호화 키를 이용한 암호화        두 번째 암호화 키를 이용한 암호화     첫 번째 암호화 키를 이용한 암호화

복호화도 똑같이.

 

3. AES 알고리즘
(Advanced Encryption Standard): des가 약해지며 개발된 알고리즘으로 128비트 암호화 블록, 다양한 키의 길이(128/192/256비트)를 갖춘 알고리즘

 

4. SEED 알고리즘
: 한국인터넷진흥원과 국내 암호 전문가들이 순수 국내 기술로 개발한 128비트 블록의 암호화 알고리즘.

https://ko.wikipedia.org/wiki/SEED

 
SEED - 위키백과, 우리 모두의 백과사전

 

ko.wikipedia.org
 

5. ARIA 알고리즘
: 경량 환경 및 하드웨어의 효율성 향상을 위해 개발된 128비트 블록 암호 알고리즘. AES와 같은 암호화 키를 지원

 

6. 양자암호
(quantum cryptography) 또는 키 분배(quantum key distribution) : 양자 역학의 복제 불가능성 원리와 측정 후 붕괴라는 현상을 이용하는 것으로 파장이나 진폭 등으로 통신하는 일반적인 통신과 달리 양자 암호는 광자(photon) 하나하나 단위로 신호를 실어 나른다. 광자 단위로 편광이나 위상차를 이용하여 신호를 전송하며, 송신 측에서도 편광 패드나 간섭계를 사용하여 측정한다.

 

7. 기타 대칭형 알고리즘
 - IDEA 알고리즘(International Data Encryption Algorithm): 128비트의 키를 사용하여 64비트의 평문을 8라운드를 거쳐 64 비트 암호문으로 만들고 모든 연산이 16비트 단위로 이루어지도록 하여 16비트 프로세서에서 구현이 용이하며 주로 키 교환에 쓰인다.

 

 - RC5 알고리즘(Ron's Code 5): 입출력, 키, 라운드 수가 가변이고 32, 64, 128 비트 키가 사용되며 속도는 des의 10배다.

 

 - Skipjack 알고리즘: 미국 NSA에서 개발한 클리퍼 칩에 내장된 블록 알고리즘으로 전화기와 같이 음성을 암호화하는데 주로 사용되며 64비트의 입출력, 80비트의 키를 이용하여 총 32라운도의 암호화 과정을 수행.

 

 - LEA 알고리즘: 고속 환경 및 모바일 기기 등의 경량 환경에서 기밀성을 제공하기 위해 국내에서 개발된 암호화 알고리즘으로  128비트 데이터 블록으로 128, 192, 256비트 비밀키를 사용

 

03. 비대칭 암호화 방식
AES가 복호화가 거의 불가능한 알고리즘으로 됐는데 대칭 암호화 방식의 큰 단점인 암호화 키를 전달하는 문제가 있다.

평문을 암호화하면 복호화하는 사람도 암호화 키를 가지고 있어야 하므로 암호문을 만든 사람이 복호화할 사람에게 암호화 키를 암호문과 같이 전달하게 됨.

 

1. 비대칭 암호화 방식의 발견
*예시 연습문제 9번

2. RSA 알고리즘
: 중요 정보를 소수 2개로 표현한 후 두 소수의 곱을 힌트와 함께 전송하여 암호로 사용.

오늘날 산업 표준으로 사용되고 충분히 큰 두 소수의 곱에서 두 소수를 찾기 어려운 점을 이용한 것으로 소수 250자리가 사용된다.

 

ex) 모든 사람이 고유한 N의 값(두 소수의 곱)을 가진다 -> N=p * q / 175,828,273 = 17,159 * 10,247

 영희가 p = 17,159, q = 10,247의 곱을 자신의 N의 값으로 정하면 공개키 N의 값이 모든 사람에게 공개되는 식.

영희에게 메시지를 보내려면 N의 값을 이용해 알고리즘으로 암호화한 후 보낸다. 영희의 개인 키는 p와 q다.

값을 금방 알아낼 것 같지만 그렇지 않은 모양이다. 예시를 보자.

 

RSA 예시)


 

3. 비대칭 암호화의 구조
 -공개키는 서로 얻을 수 있지만 서로의 개인 키는 얻을 수 없다.

 -대칭 암호화 알고리즘과 달리 메시지의 암호화와 복호화가 같은 키로 이루지지 않는다. 언제나 한 쌍의 개인 키와

공개 키로 암호화와 복호화가 이루어져서 철수의 개인 키로 암호화된 메시지는 철수의 개인 키로 복호화되지 않고 오직 철수의 공개 키로만 복호화된다.

 

평문 -암호화-> 암호문 -복호화-> 평문            평문 -암호화-> 암호문 -복호화-> 평문

    철수의 개인키          공개키                           공개키                개인키

 

4. 비대칭 암호화의 기능
 -기밀성(confidentiality) 기밀성 확보를 위한 암호화: 수신자의 공개 키로 암호화하여 송신

  ex) 철수가 영희에게 편지를 보내는데 영희만 읽게 하려면

철수가 영희의 공개 키를 구하고 영희의 공개키를 이용하여 편지를 암호화한 후 보내면 영희는 자신이 가진 개인 키를 이용해 철수의 편지를 복호화하여 읽는다.

 

 -부인방지(non-repudiation) 부인 방지 확보를 위한 암호화: 발신자의 개인 키로 암호화하여 송신

 

04. 해시
: 하나의 문자열을 이를 상징하는 더 짧은 길이의 값이나 키로 변환하는 것으로 암호화와는 다른 개념이다.

암호가 정보를 숨기는 것이라면 해시는 정보의 위/변조를 확인하기 위한 것으로 정보의 무결성을 확인하기 위한 것이다

 

 특징
-해시는 평문의 길이에 상관없이 해시 결과의 길이가 모두 같고 평문이 아주 조금만 달라도 결과를 추측하기 불가능할 정도로 다르게 나타난다.

ex) sunshine - MD5 알고리즘을 거치고-> 결과로 05717 EFMKELAM.. 의 알 수 없는 값이 나온다.(추측 불가능)

MD5 알고리즘은 32개의 16진수로 이루어져 있으며 16의 32 승개의 결과 값이 존재. 사실상 무한에 가깝기 때문에 다른 값의 데이터를 입력하더라도 해시 결과 값이 같을 수 있다.(=충돌)

충돌이 자주 일어나면 해시가 무력화되는 위험이 있다.

 

종류
MD, SHA, RMD160, TIGER, HAVAL..

-MD(Message Digest function 95) : 공개 키 기반 구조를 만들기 위해 RSA와 함께 개발한 것으로 32비트 컴퓨터에 최적화되었다.

-SHA(Secure Hash Algorithm) :MD4의 발전 형태로 160비트의 값을 생성하는 해시 함수로 데이터를 512비트의 블록으로 입력한다.
```
 
