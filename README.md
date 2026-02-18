# vestauth

auth for agents–from the creator of [`dotenv`](https://github.com/motdotla/dotenv) and [`dotenvx`](https://github.com/dotenvx/dotenvx)

[website](https://vestauth.com) · [repo](https://github.com/vestauth/vestauth) · [docs](https://vestauth.com/docs)

---

## why vestauth

agents need identity, not shared secrets.

`vestauth` replaces api keys and passwords with cryptographic identity:
- agents sign requests with a private key
- providers verify with the public key
- no shared-secret sprawl
- easier attribution, rotation, and trust

---

## quickstart

```bash
npm i -g vestauth
vestauth agent init
vestauth agent curl https://api.vestauth.com/whoami --pp
```

or:

```bash
curl -sSf https://vestauth.sh | sh
vestauth agent init
```

---

## agent side

- create a cryptographic agent identity
- sign outbound http requests automatically
- use standard signature headers compatible with web-bot-auth/http message signatures

---

## provider side

```js
const agent = await vestauth.provider.verify(req.method, url, req.headers)
```

- verify signed requests in one line
- trust agent identity from cryptographic proof
- remove username/password + api key management overhead

---

## links

- main repo: https://github.com/vestauth/vestauth
- npm: https://www.npmjs.com/package/vestauth
- company site: https://vestauth.com
