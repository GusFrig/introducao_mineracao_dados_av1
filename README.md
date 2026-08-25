# Introdução à mineração de dados -> Av1


# Busca no Espaço de Hipóteses (Algoritmo 2)

Este projeto consiste na implementação em Python de uma variante do **Algoritmo 2** para busca e avaliação exaustiva no espaço de hipóteses, aplicado a um conjunto de treinamento binário.

---

## 📌 Descrição do Problema

O objetivo do algoritmo é enumerar um espaço de hipóteses formado por conjunções lógicas de **até 3 variáveis** (incluindo suas negações) e identificar qual(is) conjunção(ões) obtém(êm) a **maior taxa de acerto** (acurácia bruta) no conjunto de dados fornecido.

---

## ⚙️ Regras e Funcionamento

1. **Conjunto de Treinamento:**
   - Vetores binários no espaço $\{0, 1\}^n$.
   - Armazenado em memória como um dicionário com duas listas (`0` e `1`), contendo $n$-tuplas.
   - Parâmetros do gerador:
     - `n`: Dimensão dos vetores.
     - `s`: Semente (*seed*) para o gerador pseudoaleatório.

2. **Espaço de Hipóteses:**
   - Composto por todas as conjunções possíveis envolvendo **até 3 variáveis** ou suas negações.
   - Exemplos de conjunções válidas:
     - $(x_1, x_3)$
     - $(x_7, \neg x_2, x_4)$
     - $(x_1, \neg x_5, \neg x_6)$

---

## 📊 Métrica de Avaliação

A taxa de acerto de uma conjunção $h$ é calculada pelo percentual de exemplos classificados corretamente em relação ao total de exemplos:

$$\text{Taxa de Acerto} = \frac{\text{Número de exemplos classificados corretamente}}{\text{Número total de exemplos}}$$

- **Classificação:** Uma hipótese atribui classe `1` a um exemplo se todas as suas condições forem satisfeitas pelo vetor; caso contrário, atribui classe `0`.

---

## 💻 Exemplo de Execução

Ao executar o script para $n = 4$ e $s = 123$:

### **Entrada (Exemplos Gerados):**
```text
n = 4
s = 123

Classe 0 (8 exemplos):
	(0, 1, 1, 0)
	(0, 0, 0, 1)
	(1, 0, 1, 0)
	(0, 0, 0, 0)
	(1, 1, 0, 1)
	(0, 1, 1, 0)
	(1, 0, 1, 0)
	(0, 0, 1, 1)

Classe 1 (7 exemplos):
	(0, 1, 1, 1)
	(1, 0, 0, 0)
	(0, 1, 1, 1)
	(1, 1, 0, 0)
	(1, 1, 1, 0)
	(0, 0, 1, 0)
	(1, 0, 0, 0)
