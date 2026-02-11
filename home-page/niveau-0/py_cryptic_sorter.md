# py\_cryptic\_sorter

{% hint style="danger" %}
Sujet buggé, conflit entre un exemple du sujet et celui de la moulinette, suivre la moulinette dans ce cas !
{% endhint %}

Le but de cet exercice est d'écrire une fonction qui trie une chaine de charactères selon 3 critères :

1. Il faut d'abord trier les chaines de charactères selon leur longueur,
2. Ensuite si deux chaines de charactères sont de même longueur il faut les trier dans l'ordre alphabétique.
3. Finalement si deux chaines de charactères sont de même longueur, il faut les trier selon leur nombre de voyelles

```python
def py_criptic_sorter(strings : list[str]) -> list[str]
```

Voici quelques exemples d'exécutions de la fonction avec la sortie attendue :

```python
print(py_criptic_sorter(["chat", "chien", "oiseau", "ane", "elephant", "abeille"]))
# ["ane", "chat", "chien", "abeille", "oiseau", "elephant"]
print(py_criptic_sorter(["a1b2", "c3b4", "g7h8", "e5f6"]))
# ["a1b2", "c3b4", "e5f6", "g7h8"]
print(py_criptic_sorter(['APPLE', 'Apple', 'apple']))
# ['APPLE', 'apple', 'Apple']
print(py_criptic_sorter([]))
# 
print(py_criptic_sorter([""]))
# 
```

<details>

<summary>Version sorted</summary>

```python
def count_vowels(s : str) -> int:
    vowels = 'aeiouyAEIOUY'
    return sum(1 for c in s if c in vowels)

def py_criptic_sorter(strings : list[str]) -> list[str]:
    return sorted(chaines, key=lambda s: (len(s), s, count_vowels(s)))
```

</details>

<details>

<summary>Version for</summary>

```python
def count_vowels(s: str) -> int:
    voyelles = "aeiouyAEIOUY"
    count = 0
    for c in s:
        if c in voyelles:
            count += 1
    return count

def py_criptic_sorter(strings: list[str]) -> list[str]:
    n = len(strings)

    for i in range(n):
        for j in range(0, n - i - 1):
            a = strings[j]
            b = strings[j + 1]

            swap = False

            # 1) longueur
            if len(a) > len(b):
                swap = True

            # 2) si même longueur → ordre alphabétique
            elif len(a) == len(b) and a > b:
                swap = True

            # 3) si même longueur ET même mot → nombre de voyelles
            elif len(a) == len(b) and a == b and count_vowels(a) > count_vowels(b):
                swap = True

            if swap:
                strings[j], strings[j + 1] = strings[j + 1], strings[j]

    return strings
```

</details>
