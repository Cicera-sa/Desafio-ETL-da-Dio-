# Desafio-ETL-da-Dio-
Este projeto tem o objetivo de exercitar a Extração, transformação e carregamentos de dados de forma fictícia.  
Exercicio: Carregar uma planilha no formato CVS no Python, extrair desta planilha as informações preenchidas dos clientes, pelo UserID
Alteração e transformação de dados de dados: Adicionar uma coluna para cada UserID de crédito de R$100,00 

Primeiro código feito: 
mport pandas as pd

# Etapa 1: Extração (Extract)
# Vamos extrair os dados do arquivo CSV
dados = pd.read_csv('seuarquivo.csv')

# Examinar os dados após a extração
print("Dados extraídos:")
print(dados.head())

# Etapa 2: Transformação (Transform)
# Filtre os dados para manter apenas as informações dos clientes (IDs 1, 3 e 5)
clientes = dados[dados['ID'].isin([1, 3, 5])]

# Crie a nova coluna "novo crédito disponível" com o valor de 100,00 para cada cliente
clientes['novo crédito disponível'] = 100.00

# Examine os dados após a transformação
print("\nDados após a transformação:")
print(clientes)

# Etapa 3: Carga (Load)
# Vamos salvar os dados transformados em um novo arquivo CSV
clientes.to_csv('clientes_enriquecidos.csv', index=False)

print("\nDados transformados carregados em 'clientes_enriquecidos.csv'.")

Este código deu erro, pois na planilha original a coluna id estava escrita como UserID, então para correção temos o código abaixo: 
import pandas as pd

caminho_do_arquivo = 'C:\\Users\\Ci\\Downloads\\SDW2023.csv.csv'
dados = pd.read_csv(caminho_do_arquivo)
print("Dados extraídos:")
print(dados.head())
clientes = dados[dados['UserID'].isin([1, 3, 5])]

# Imprima os dados dos clientes
print("Clientes:")
print(clientes)

Resultado da impressão: 
Dados extraídos:
   UserID      Nome    Conta  Agencia 
0       1   Fernanda  0001-1       1.0
1       2        NaN     NaN       NaN
2       3     Cicera  0001-2       2.0
3       4        NaN     NaN       NaN
4       5  Cristina   0001-3       3.0
Clientes:
   UserID      Nome    Conta  Agencia 
0       1   Fernanda  0001-1       1.0
2       3     Cicera  0001-2       2.0
4       5  Cristina   0001-3       3.0
PS C:\Users\Ci> 

Segundo código feito:
# Adicione uma nova coluna "Novo Crédito Disponível" com o valor de R$100,00
clientes['Novo Crédito Disponível'] = 100.0

# Imprima os dados atualizados dos clientes
print("Clientes com Novo Crédito Disponível:")
print(clientes)



