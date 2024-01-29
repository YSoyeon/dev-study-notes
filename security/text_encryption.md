# 문자열 암호화

## 암호화 종류

### 단방향 암호화

평문을 암호화 한 뒤 복호화할 수 없다. (대표적인 예 : `SHA-256`)

### 양방향 암호화

암호화 <-> 복호화 (대표적인 예 : `AES-256`)

- 대칭키 : 암호화하고 복호화 하는 데 사용되는 키가 동일
- 비대칭키 : 암호화와 복호화에 각각 다른 키가 사용됨

## 기본 원리

### 암호화

- plain text 👉 plain bytes 👉 encrypt 👉 encrypted bytes 👉 encrypted base64 test

### 복호화

- encrypted base64 text 👉 encrypted bytes 👉 decrypt 👉 plain bytes 👉 plain text

### 구성요소

- **plain text** : 평문, 암호화되기 전 원본 데이터

- **key** : 암호화 및 복호화를 수행하는 데 사용되는 비밀 값 <br />
  (AES256에서는 256비트의 키를 사용)

- **initialization vector(IV)** : 초기화 벡터, 암호화 과정에서 블록 암호화를 수행하는 데 사용되는 비밀 값으로 복호화 시에도 사용

- **CipherText** : 암호문, 평문을 암호화한 결과

- **암호화 알고리즘** : AES256에서는 AES(Advanced Encryption Standard) 암호화 알고리즘을 사용, AES는 블록 암호화 알고리즘으로, 128비트 블록 단위로 데이터를 처리

- **padding** : 데이터 블록의 길이가 블록 크기의 배수가 아닐 경우, 마지막 블록에 패딩을 추가하여 블록 크기의 배수로 맞추는 작업

- **Operation Mode** : 운영 모드, 데이터 블록을 처리하는 방법 <br />
  (AES256에서는 CTR(Counter) 운영 모드 사용)

## 블록 암호화

> 고정된 길이의 블록 단위로 데이터를 나누어 암호화하는 대칭키 암호화 기법
