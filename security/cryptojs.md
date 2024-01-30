# CryptoJS

js에서 데이터를 쉽게 암호화할 수 있게 해주는 라이브러리

## 암호화 방식

- `대칭키` : 암/복호화할 때 같은 키값을 사용 <br />
  (ex. DES, AES, SEED ...)
- `비대칭키` : 암/복호화할 때 다른 키값을 사용<br />
  (ex. RSA, ECC, DSS...)
- `해싱` : 단방향으로 암호화만 가능하고 복호화 불가능<br />
  (ex. MD5, SHA-0, SHA-1...)

## encrypt

> 주어진 값을 암호화

```js
CryptoJS.AES.encrypt(text, 'YOUR_SECRET_KEY');
```

## descrypt

> 주어진 값을 복호화

```js
CryptoJS.AES.descrypt(encryptedText, 'YOUR_SECRET_KEY');
```
