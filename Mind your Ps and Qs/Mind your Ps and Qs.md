Author: Sara

#### Description

In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/2604f8b51a5cc62d38a3736938f19cef/values)

#### Solution

Open `values` it contains

```values
Decrypt my super sick RSA:
c: 861270243527190895777142537838333832920579264010533029282104230006461420086153423
n: 1311097532562595991877980619849724606784164430105441327897358800116889057763413423
e: 65537
```

Using https://www.dcode.fr/rsa-cipher we can provide the values for `c`, `n`, and `e` and get a result

Answer: `picoCTF{sma11_N_n0_g0od_13686679}`