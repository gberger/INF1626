# INF1626 - Formal Languages and Automata

**2014.1**

Project for the Formal Languages and Automata course at PUC-Rio.


## Project 

Build an [Universal Turing Machine](https://en.wikipedia.org/wiki/Universal_Turing_machine) on [JFLAP](http://www.jflap.org/).


## Encoding

Note: `+` indicates one or more, and `|` indicates OR.

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

### Examples

