import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Configurações de exibição
pd.set_option('display.max_columns', None)
sns.set(style="whitegrid")

# Caminho para o arquivo Excel
caminho_arquivo = r'C:\Users\geana\Downloads\Base Devoluções.xlsx'

# Leitura do arquivo Excel
dados = pd.read_excel(caminho_arquivo)

# Análise exploratória dos dados
print("Informações básicas do conjunto de dados:")
print(dados.info())

# Verificando as primeiras linhas do DataFrame
print("\nPrimeiras linhas do DataFrame:")
print(dados.head())

# Análise estatística dos dados
print("\nAnálise estatística dos dados:")
print(dados.describe())

# Verificando valores únicos em cada coluna
print("\nValores únicos em cada coluna:")
for coluna in dados.columns:
    print(coluna + ':', dados[coluna].nunique())

# Verificando valores ausentes
print("\nValores ausentes:")
print(dados.isnull().sum())

# Visualização dos dados

# Gráfico de pizza para mostrar a distribuição dos motivos de devolução
plt.figure(figsize=(10, 6))
motivos_devolucao = dados['Motivo Devolução'].value_counts()
motivos_devolucao.plot(kind='pie', autopct='%1.1f%%', startangle=90, explode=(0.1, 0, 0, 0, 0))
plt.title('Distribuição dos Motivos de Devolução')
plt.ylabel('')
plt.show()

# Gráfico de barras para mostrar a contagem de devoluções por cliente
plt.figure(figsize=(12, 8))
devolucoes_por_cliente = dados['Nome do Cliente'].value_counts().head(10)
sns.barplot(x=devolucoes_por_cliente.values, y=devolucoes_por_cliente.index, palette='viridis')
plt.title('Top 10 Clientes com Maior Número de Devoluções')
plt.xlabel('Número de Devoluções')
plt.ylabel('Nome do Cliente')
plt.show()

# Gráfico de contagem de devoluções por categoria de produto
plt.figure(figsize=(12, 8))
sns.countplot(y='Categoria', data=dados, order=dados['Categoria'].value_counts().index, palette='Set2')
plt.title('Contagem de Devoluções por Categoria de Produto')
plt.xlabel('Número de Devoluções')
plt.ylabel('Categoria de Produto')
plt.show()

# Boxplot para visualizar a distribuição dos valores devolvidos por categoria de produto
plt.figure(figsize=(12, 8))
sns.boxplot(x='Categoria', y='Valor Devolvido', data=dados, palette='Pastel1')
plt.title('Distribuição dos Valores Devolvidos por Categoria de Produto')
plt.xlabel('Categoria de Produto')
plt.ylabel('Valor Devolvido')
plt.xticks(rotation=45)
plt.show()

# Análise temporal das devoluções
dados['Ano'] = dados['Data Devolução'].dt.year
plt.figure(figsize=(12, 8))
sns.countplot(x='Ano', data=dados, palette='BuGn')
plt.title('Número de Devoluções ao Longo dos Anos')
plt.xlabel('Ano')
plt.ylabel('Número de Devoluções')
plt.show()

# Scatter plot para visualizar a relação entre o valor da devolução e a quantidade devolvida
plt.figure(figsize=(10, 6))
sns.scatterplot(x='Quantidade Devolvida', y='Valor Devolvido', data=dados, hue='Categoria', palette='Dark2')
plt.title('Relação entre Quantidade e Valor Devolvido por Categoria de Produto')
plt.xlabel('Quantidade Devolvida')
plt.ylabel('Valor Devolvido')
plt.show()



Versao atualizada



import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Configurações de exibição
pd.set_option('display.max_columns', None)
sns.set(style="whitegrid")

# Caminho para o arquivo Excel
caminho_arquivo = r'C:\Users\geana\Downloads\Base Devoluções.xlsx'

# Leitura do arquivo Excel
dados = pd.read_excel(caminho_arquivo)

# Análise exploratória dos dados
print("Informações básicas do conjunto de dados:")
print(dados.info())

# Verificando as primeiras linhas do DataFrame
print("\nPrimeiras linhas do DataFrame:")
print(dados.head())

# Análise estatística dos dados
print("\nAnálise estatística dos dados:")
print(dados.describe())

# Verificando valores únicos em cada coluna
print("\nValores únicos em cada coluna:")
for coluna in dados.columns:
    print(coluna + ':', dados[coluna].nunique())

# Verificando valores ausentes
print("\nValores ausentes:")
print(dados.isnull().sum())

# Visualização dos dados

# Gráfico de pizza para mostrar a distribuição dos motivos de devolução
plt.figure(figsize=(10, 6))
motivos_devolucao = dados['Motivo Devolução'].value_counts()
motivos_devolucao.plot(kind='pie', autopct='%1.1f%%', startangle=90, explode=(0.1, 0, 0, 0, 0))
plt.title('Distribuição dos Motivos de Devolução')
plt.ylabel('')
plt.show()

# Gráfico de barras para mostrar a contagem de devoluções por cliente
plt.figure(figsize=(12, 8))
devolucoes_por_cliente = dados['Nome do Cliente'].value_counts().head(10)
sns.barplot(x=devolucoes_por_cliente.values, y=devolucoes_por_cliente.index, palette='viridis')
plt.title('Top 10 Clientes com Maior Número de Devoluções')
plt.xlabel('Número de Devoluções')
plt.ylabel('Nome do Cliente')
plt.show()

# Gráfico de contagem de devoluções por categoria de produto
plt.figure(figsize=(12, 8))
sns.countplot(y='Categoria', data=dados, order=dados['Categoria'].value_counts().index, palette='Set2')
plt.title('Contagem de Devoluções por Categoria de Produto')
plt.xlabel('Número de Devoluções')
plt.ylabel('Categoria de Produto')
plt.show()

# Boxplot para visualizar a distribuição dos valores devolvidos por categoria de produto
plt.figure(figsize=(12, 8))
sns.boxplot(x='Categoria', y='Valor Devolvido', data=dados, palette='Pastel1')
plt.title('Distribuição dos Valores Devolvidos por Categoria de Produto')
plt.xlabel('Categoria de Produto')
plt.ylabel('Valor Devolvido')
plt.xticks(rotation=45)
plt.show()

# Análise temporal das devoluções
dados['Ano'] = dados['Data Devolução'].dt.year
plt.figure(figsize=(12, 8))
sns.countplot(x='Ano', data=dados, palette='BuGn')
plt.title('Número de Devoluções ao Longo dos Anos')
plt.xlabel('Ano')
plt.ylabel('Número de Devoluções')
plt.show()

# Scatter plot para visualizar a relação entre o valor da devolução e a quantidade devolvida
plt.figure(figsize=(10, 6))
sns.scatterplot(x='Quantidade Devolvida', y='Valor Devolvido', data=dados, hue='Categoria', palette='Dark2')
plt.title('Relação entre Quantidade e Valor Devolvido por Categoria de Produto')
plt.xlabel('Quantidade Devolvida')
plt.ylabel('Valor Devolvido')
plt.show()
