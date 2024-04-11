# Flipped
- As the challenge name suggests, the session cookies are vulnerable to bit-flipping attack.

- # What is a bit-flipping attach?
  A bit-flipping attack in web security targets the integrity of data by manipulating individual bits within it. It aims to tamper with the information being transmitted or stored.

- Now, why is this a bit-flipping attack challange?
- 1. AES-128-CBC is used to encrypt/decrypt the session cookie (see https://crypto.stackexchange.com/questions/66085/bit-flipping-attack-on-cbc-mode for more info).
  2. The server does not verify the integrity of the session cookie.

- Here in the challange we can see that the ```admin``` value is ```0``` in ```{"admin": 0, "username": "guest"}```. now our goal is to chnage the value to a non zero value to get the flag.
- The initial session cookie has an ASCII zero (0x30) at offset 10, so we just need to flip the least-significant bit in the ciphertext byte to result in an ASCII one (0x31) for the corresponding plaintext byte.
- So for that we will be writing a code, which follows to be like:
```
import requests
from base64 import b64decode, b64encode

url = "//put up the following url here!!//"
default_session = '{"admin": 0, "username": "guest"}'
res = requests.get(url)
c = bytearray(b64decode(res.cookies["session"]))
c[default_session.index("0")] ^= 1
evil = b64encode(c).decode()
res = requests.get(url, cookies={"session": evil})
print(res.text)
```
- By running the above code, we can get the flag.
