# py\_mirror\_matrix

Le but de cet exercice est de renvoyer le miroir d'une matrice passée en entrée.

```python
def py_mirror_matrix(matrix: list[list[int]]) -> list[list[int]]
```

Voici quelques exemples d'exécutions de la fonction avec la sortie attendue :

```python
print(py_mirror_matrix([[1, 2, 3], [4, 5, 6], [7, 8, 9]]))
# [[3, 2, 1], [6, 5, 4], [9, 8, 7]]
print(py_mirror_matrix([[4], [5]]))
# [[4], [5]]
print(py_mirror_matrix([[1, 2], []]))
# [[2, 1], []]
print(py_mirror_matrix([]))
# []
```

<details>

<summary>Version avec l'opérateur de slicing</summary>

```python
def py_mirror_matrix(matrix):
    return [row[::-1] for row in matrix]
```

</details>

<details>

<summary>Version itérative</summary>

```python
def py_mirror_matrix(matrix):
    mirrored = []
    for row in matrix:
        mirrored.append(list(reversed(row)))
    return mirrored
```

</details>
