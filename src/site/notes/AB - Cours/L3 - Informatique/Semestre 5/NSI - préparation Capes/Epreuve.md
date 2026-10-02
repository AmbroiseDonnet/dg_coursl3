---
{"dg-publish":true,"permalink":"/AB - Cours/L3 - Informatique/Semestre 5/NSI - préparation Capes/Epreuve/","created":"2026-10-02T12:54:35.749+02:00","updated":"2026-10-02T14:51:13.658+02:00","dg-note-properties":{}}
---

# Épreuve du capes n°2

## Exercice 1

### Partie A

#### Question 1:

43 = 32 + 0 + 8 + 0 + 2 + 1 s'écrit donc en binaire 101011
#### Question 2:

100010 = 2⁵ + 2² = 2 + 32 = 34

#### Question 3:

En itératif:

```python
def decimal_vers_binaire(n : int) -> str
	chaine = ""
	while n > 2:
		chaine += str(n%2) + chaine
		n = n // 2
	return str(n%2) + chaine
```

En récursif:

```python
def decimal_vers_binaire(n : int) -> str
	if n < 2:
		return str(n) 
	return decimal_vers_binaire(n//2) + str(n%2)
	
```

#### Question 4:

En itératif: (Algorithme de Hörner)
```python
def binaire_vers_decimal(b : str) -> int
	res = 0
	while len(b) >= 1:
		res = 2 * res + int(b[0])
		b = b[1:]

```
En récursif: (N'est pas optimiser il fait beaucoup d'opération)
```python
ALPHABET = "01"
def binaire_vers_decimal(b : str) -> int
	if len(b) >= 1 :
		return ALPHABET.index(b[0]) * 2 ** (len(b) - 1) + binaire_vers_entier(b[1:])
	else:
		return 0

```
Algorithme de Hörner
```python
def binaire_vers_decimal(b : str) -> int
	if len(b) >= 1 :
		return 2* binaire_vers_entier(b[0:1]) + int(b[-1])
	else:
		return 0
```

### Partie B: Manipulation de Bits

a = 12 (10)
b = 25 (10)

12 =>  8 + 4 + 0 + 0 => 0000 1100
25 => 16 + 8 + 0 + 0 + 1 => 0001 1001
#### Question 5 :



a & b => 0000 1000 => 8
~ a => 1111 0011 => 128 + 64 + 32 + 16 + 0 + 0 + 2 + 1  (le complément à 2) + 1 = 244
a >> 2 => 0000 0110 => 3 (⚠ : ça décale de 2 pas de 1)

#### Question 6 :

```python
def est_pair(n : int) -> bool
	return n & 1 == 0
```

```python
def extraire_bits(n: int, d: int, long: int) -> int:
	masque = 2**long - 1 = (1 << long) - 1
	return (n >> d) & masque
```

### Partie C : Traitement d'imagerie médicale

#### Question 8

```python
matrices = [[pixels[largeur * i + j]]
			for j in range(largeur)
			for i in range(hauteur)]
```

## to-do for 9 octobre

- [ ] Finir exercice 1
- [ ] Faire exercice 2