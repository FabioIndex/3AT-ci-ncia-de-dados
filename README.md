# 3AT-ciencia-de-dados

# Passo 1: Abrir o Google Colab e Criar um Notebook
## Acesse 
### colab.research.google.com.
 Clique em "Novo notebook".
 Renomeie o notebook (ex: Aprendendo_Pandas.ipynb) clicando no nome na parte superior. 
# Passo 2: Importar a Biblioteca Pandas 
 No primeiro "célula de código", importe o pandas. O padrão é usar o alias pd. 

 python
 import pandas as pd
 import numpy as np # Opcional, mas útil para dados numéricos

Clique no botão "Play" (ou pressione Shift + Enter) para rodar a célula. 
# Passo 3: Criar um DataFrame (Dados Fictícios) 
## Vamos criar um DataFrame simples para começar.

python
data = {
    'Nome': ['Ana', 'Bruno', 'Caio', 'Diana'],
    'Idade': [25, 30, 22, 35],
    'Cidade': ['São Paulo', 'Rio', 'Rio', 'Curitiba'],
    'Salário': [5000, 7000, 4000, 8000]
}

df = pd.DataFrame(data)
# Exibir o DataFrame
df
# Passo 4: Explorar os Dados (Básico)
Ver as primeiras linhas: 
df.head(2)
Ver informações sobre tipos de dados: 
df.info()
Resumo estatístico: 
df.describe()
Dimensões do DataFrame (linhas, colunas): 
df.shape 
# Passo 5: Manipular e Filtrar Dados
### 1. Selecionar uma coluna:

python
idades = df['Idade']
print(idades)
### 2. Filtrar linhas (ex: Pessoas com mais de 28 anos):
python
filtro = df[df['Idade'] > 28]
python
df['Senior'] = df['Idade'] > 30
print(df)

# Passo 6: Ordenar e Agrupar
1. Ordenar por salário (decrescente):
python.
### df_ordenado = df.sort_values(by='Salário', ascending=False)
### print(df_ordenado)
2. Agrupar por Cidade e calcular a média de salário:
python
media_salario = df.groupby('Cidade')['Salário'].mean()
print(media_salario)
Passo 7: Salvar/Exportar seus dados
Você pode salvar o resultado em um arquivo CSV: 
python
df.to_csv('dados_finalizados.csv', index=False)
Para baixar o arquivo: Clique no ícone de "Pasta" na barra lateral esquerda, encontre o arquivo, clique nos três pontinhos e selecione "Download".
Exemplo Prático: Lendo um arquivo CSV no Colab
Se você tiver um arquivo .csv no seu computador:
Clique na pasta "Arquivos" no menu esquerdo do Colab.
Clique no ícone de "Upload" e envie seu CSV.
Use o comando abaixo:
python
df = pd.read_csv('nome_do_seu_arquivo.csv')
df.head()
Resumo dos Comandos Principais
Ação 	Comando
Importar	import pandas as pd
Ler CSV	pd.read_csv('arquivo.csv')
Ver Dados	df.head()
Ver Tipos	df.info()
Filtrar	df[df['coluna'] > valor]
Agrupar	df.groupby('coluna').mean()
