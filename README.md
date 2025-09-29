import pandas as pd
import matplotlib.pyplot as plt

# Simulando um conjunto de dados
dados = {
    'Produto': ['Arroz', 'Feijão', 'Macarrão', 'Arroz', 'Feijão', 'Macarrão'],
    'Quantidade': [10, 5, 8, 7, 3, 6],
    'Preço Unitário': [5.0, 4.5, 3.0, 5.0, 4.5, 3.0]
}

df = pd.DataFrame(dados)

# Criando uma nova coluna com o total da venda
df['Total'] = df['Quantidade'] * df['Preço Unitário']

# Agrupando por produto
resumo = df.groupby('Produto')['Total'].sum().reset_index()

print("Resumo de vendas por produto:")
print(resumo)

# Visualizando os dados
plt.bar(resumo['Produto'], resumo['Total'], color='skyblue')
plt.title('Total de Vendas por Produto')
plt.xlabel('Produto')
plt.ylabel('Total em R$')
plt.show()


