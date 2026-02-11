# py\_bracket\_validator

Le but de cet exercice est d'écrire une fonction qui vérifie si une chaine de charactères est bien parenthésée. Il faut gérer les trois types de parenthèses : (), \[], {}.

```python
def py_bracket_validator(s : str) -> bool
```

***

Voici quelques exemples d'exécutions de la fonction avec la sortie attendue :

```bash
python3 py_bracket_validator.py "()"
True
python3 py_bracket_validator.py "{()}"
True
python3 py_bracket_validator.py "(()"
False
python3 py_bracket_validator.py "()[]"
True
python3 py_bracket_validator.py "()[]"
True
python3 py_bracket_validator.py "([)]"
False
python3 py_bracket_validator.py "{Hello}[World](!)"
True
```

> [!NOTE]
> Dans les exemples d'exécutions ci-dessus je mets le paramètre de la fonction en argument mais il n'est pas demandé de faire ça pour l'examen.


***

#### Implémentation de la solution

<details>

<summary>py_bracket_validator</summary>

{% code title="py_bracket_validator.py" lineNumbers="true" fullWidth="false" %}
```python
def bracket_validator(s: str) -> bool:
	brackets = []
	correspondances = {")" : "(", "]" : "[", "}" : "{"}
	for c in s:
		if c in "{([":
			brackets.append(c)
		elif c in "}])":
			if not brackets or brackets.pop() != correspondances[c]:
				return False
	return len(brackets) == 0
```
{% endcode %}

</details>
