# py\_palindrome\_validator

Le but de cet exercice est d'écrire une fonction python qui vérifie si une chaine de charactère est palindrome. La fonction ne doit prendre en compte que les charactères alphabétiques et ignorer les autres.&#x20;

```python
def is_palindrome(s: str) -> bool
```

Voici quelques exemples d'exécutions de la fonction avec la sortie attendue :

```bash
print(is_palindrome("A man, a plan, a canal: Panama"))
# True
print(is_palindrome("race a car"))
# False
print(is_palindrome("Was it a car or a cat I saw?"))
# True
print(is_palindrome(" "))
# True
print(is_palindrome("No 'x' in Nixon"))
# True
```

<details>

<summary>Version filter</summary>

```python
def is_palindrome(s: str) -> bool:
    res = ''.join(filter(str.isalnum, s)).lower()
    return res == res[::-1]
```

</details>

<details>

<summary>Version itérative</summary>

```python
def is_valid_palindrome(s: str) -> bool:
    cleaned = []

    for c in s:
        if c.isalnum():
            cleaned.append(c.lower())

    left, right = 0, len(cleaned) - 1

    while left < right:
        if cleaned[left] != cleaned[right]:
            return False
        left += 1
        right -= 1

    return True
```

</details>
