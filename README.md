# startsimple
How to start programming...

# Example 1
As it was:
```python3
# Instanciando uma transformação DropColumns
rm_columns = DropColumns(
    columns=['pos', 'pos\nAlt', 'Pos 2\nAlt', 'Atk\nhz', 'nome',
       '?mostaire?', 'vida+defesa \nVs ataque hz',
       'ataque hz\n* vida', '((Vida + ataque\nHz*k)*def) / 100',
       'category', 'Unnamed: 15', 'Unnamed: 16',
       'historico de formulas dos ranks', 'Unnamed: 18']  # Essa transformação recebe como parâmetro uma lista com os nomes das colunas indesejadas
)

# Definição das colunas que serão features (nota-se que a coluna NOME não está presente)
# features=variaveis de entrada
features = [
    "vida", 'ataque', 'defesa', "speed?\nAttack"
]

# Definição da variável-alvo
target = ["type"]
```
As it turned out after:
```python3
import numpy as np

# Definição das colunas que serão features (nota-se que a coluna NOME não está presente)
# features=variaveis de entrada
features = [
    "vida", 'ataque', 'defesa', "speed?\nAttack"
]

# Definição da variável-alvo
target = ["type"]

# Instanciando uma transformação DropColumns
# Essa transformação recebe como parâmetro uma lista com os nomes das colunas indesejadas
rm_columns = DropColumns(
    columns=np.setdiff1d(df_data_com_nomes_formatados.columns.array,features+target)
)
```
