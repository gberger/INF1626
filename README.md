# INF1626 - Formal Languages and Automata

**2014.1**

Project for the Formal Languages and Automata course at PUC-Rio.


## Project 

Build an [Universal Turing Machine](https://en.wikipedia.org/wiki/Universal_Turing_machine) on [JFLAP](http://www.jflap.org/).


## Encoding

Note: `+` indicates **one or more**, and `|` indicates **OR**.

```
symbolA: a1+
symbolB: b1+
symbolC: c1+
state: q1+
stateI: <state> | q
stateF: <state> | F
direction: R | L
rule: $<stateI><symbolA><symbolC><directio><stateF>
rules: <rule>+
word: #<symbolB>+

turingMachine: <rules><word>
```

`a1^n`, `b1^n` and `c1^n`, with equal `n`, all denote the same symbol. The difference is that `a` is used on the "read" part of a rule, "b" is used on the virtual tape (word), and `c` is used on the "write" part of a rule. They are only different to make it easier to read and parse.

**IMPORTANT**: `a1`, `b1` and `c1` denote the EMPTY symbol. 

### Examples

#### Primeiro

* shift para esquerda
* shift para esquerda
* encontrar transição com q < k
* encontrar transição com q > k
* encontrar transição com a < b
* encontrar transição com a > b
* encontrar transição correta e aplicar, indo para estado final
* aceita

```
$qa111c1Rq11$q1a1c1Lq$q111a1c1Lq$q11a1c1Lq$q11a111c1Lq$q11a11c11111LF#b111b11
```

#### Segundo

* não aceita

```
$qa1c1RF$qa111c111RF#b11b11
```

#### Terceiro

* lê símbolo vazio (a1)

```
$qa11c11Rq1$q1a1c111LF#a11
```