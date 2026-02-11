# py\_string\_compressor

Le but de cet exercice est de compter les caractères consécutifs identiques dans une chaine de charactères.

```python
def py_string_compressor(s: str) -> str
```

Voici quelques exemples d'exécutions de la fonction avec la sortie attendue :

```python
print(compresser("AAAABBBCCDAA"))
# "A4B3C2D1A2"
print(compresser("abc"))
# "a1b1c1"
print(compresser("Maison"))
# "M1a1i1s1o1n1"
print(compresser(""))
#
```

<details>

<summary>Version string</summary>

```python
def py_string_compressor(s: str) -> str:
    if not s:
        return ""

    res = ""
    compteur = 1

    for i in range(1, len(s)):
        if s[i] == s[i - 1]:
            compteur += 1
        else:
            res += s[i-1] + str(compteur)
            compteur = 1

    res += s[-1] + str(compteur)

    return res
```

</details>

<details>

<summary>Version tableau</summary>

```python
def compress_string(s: str) -> str:
    if not s:
        return ""

    result = []
    count = 1

    for i in range(1, len(s)):
        if s[i] == s[i - 1]:
            count += 1
        else:
            if count > 1:
                result.append(s[i - 1] + str(count))
            else:
                result.append(s[i - 1])
            count = 1

    # traiter le dernier groupe
    if count > 1:
        result.append(s[-1] + str(count))
    else:
        result.append(s[-1])

    return "".join(result)
```

</details>
