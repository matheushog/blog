---
title: "Criando cartelas de BINGO!"
date: 2022-12-29T22:13:01+01:00
categories: [code]
tags: [misc,learning]
---

# Cartelas de BINGO!

Durante a pandemia, foi necessário encontrar outras formas de arrecadar fundos para ajudar os 3 asilos, ajudados por voluntáios da [Escola de Engenharia de Lorena (EEL-USP)](https://www.eel.usp.br/) da entidade, sem fins lucrativos, [Idoso Amigo](https://www.instagram.com/idosoamigo/).

Uma forma encontrada foi a da execução de um BINGO. Tentando otimizar o trabalho de elaboração das cartelas, encontrou-se uma forma de criação das **1500** cartelas, com auxilio de programação em linguagem [python](https://www.python.org/).

Para isso contei com a ajuda de 2 pessoas que me ajudaram na elaboração do codigo, [André Luiz Guimarães de Castilho](https://www.linkedin.com/in/aluizgc/) e [Matheus Magalhães Lotufo](https://www.linkedin.com/in/theusml/).

---

## **Bibliotecas utilizadas**

```python
import random
import pandas as pd
import numpy as np
import seaborn as sns
from matplotlib.colors import ListedColormap
import matplotlib.pyplot as plt
```

---

## **Criação do *dataframe* com as colunas**
```python
def bingo(num_cartelas):
  cartao = pd.DataFrame(index=range(num_cartelas),
  columns=['B','I','N','G','O'])
  for i in range(num_cartelas):
    for j in range(5):
      lista = list(range(j*15 +1, j*15 + 16))
      numeros = random.sample(lista, 5)
      numeros.sort()
      cartao.iloc[i,j] = numeros
  return cartao
```
Neste código é expecificado o número de cartelas que serão criadas com o argumento ```num_cartelas```, e em cada coluna "B", "I", "N", "G" e "O", são agrupados de 15 em 15 os números gerados randomicamente pela biblioteca ```random```.

Com estas infomações podemos gerar um arquivo ```.csv``` com todas as cartelas geradas.
```python
# criar uma variavel que recebe as cartelas geradas, 
# neste exemplo foi gerada 1 (uma) cartela
bingoPandas = bingo(1)

# Criar o arquivo .csv 
bingoPandas.to_csv("cartelas.csv")
```

---

## **Confecção das cartelas**

```python
sns.set_theme()
fig, ax = plt.subplots(figsize=(8.88,7.47))

indice = 0

b = (np.array(bingoPandas['B'][indice]))
i = (np.array(bingoPandas['I'][indice]))
n = (np.array(bingoPandas['N'][indice]))
g = (np.array(bingoPandas['G'][indice]))
o = (np.array(bingoPandas['O'][indice]))

fig = sns.heatmap(np.matrix([b, i, n, g, o]).T,
            annot=True, fmt="d", annot_kws=({'size': 13, 'weight': 'bold'}),
            cbar=False, xticklabels=0, yticklabels=0, cmap=ListedColormap(['white']),
            linewidths=0, linecolor='black')
ax = fig

plt.show()
```

Utilizando o gráfico do tipo ```heatmap``` da biblioteca ```seaborn```, criou-se um gráfico simples que posteriormente foi acoplado a arte da entidade, para a criação das cartelas. Segue exemplo abaixo:

![Cartela de exemplo](/img/cartela_bingo.png)

Para terminar foi criado um `for loop` para a criação das **1500** cartelas e posteriormente utilizou-se a bilbioteca [opencv](https://opencv.org/), para criar as cartelas com a arte da entidade.

---