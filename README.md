--Questão 1 -- Utilizando o código fonte abaixo:
int INDICE = 13, SOMA = 0, K = 0;
Enquanto K < INDICE faça { K = K + 1; SOMA = SOMA + K; }
Imprimir(SOMA);
Resultado da soma será - 91

-- Questão 2 -- A função gera a sequência de Fibonacci em uma lista, começando com os números 0 e 1.
Cálculo da sequência: Um loop é utilizado para continuar adicionando novos números à lista até que o último número gerado seja maior ou igual ao número informado.
Verificação: A função verifica se o número está presente na lista da sequência de Fibonacci.
Saída: O programa imprime uma mensagem indicando se o número informado pertence ou não à sequência.
def pertence_a_fibonacci(numero):
    # Inicializa os primeiros elementos da sequência de Fibonacci
    fib = [0, 1]
    
    # Calcula a sequência de Fibonacci até o número informado
    while fib[-1] < numero:
        fib.append(fib[-1] + fib[-2])

    # Verifica se o número está na sequência
    if numero in fib:
        return f"O número {numero} pertence à sequência de Fibonacci."
    else:
        return f"O número {numero} não pertence à sequência de Fibonacci."

# Número previamente definido
numero_informado = 21  
resultado = pertence_a_fibonacci(numero_informado)
print(resultado)

-- Questão 3 -- O menor valor de faturamento ocorrido em um dia do mês;
O maior valor de faturamento ocorrido em um dia do mês;
Número de dias no mês em que o valor de faturamento diário foi superior à média mensal.
vamos lá:

# Exemplo de dados de faturamento diário em formato JSON
dados_faturamento = '''
{
    "faturamento": [100.0, 200.0, 150.0, 0.0, 300.0, 400.0, 0.0, 250.0, 100.0, 200.0]
}
'''

dados = json.loads(dados_faturamento)
faturamentos = dados["faturamento"]

# Calculando menor, maior e média mensal
menor_faturamento = min(filter(lambda x: x > 0, faturamentos))
maior_faturamento = max(faturamentos)
media_mensal = sum(faturamentos) / len(list(filter(lambda x: x > 0, faturamentos)))

# Contando dias acima da média
dias_acima_media = sum(1 for valor in faturamentos if valor > media_mensal)

print(f"Menor faturamento: R${menor_faturamento:.2f}")
print(f"Maior faturamento: R${maior_faturamento:.2f}")
print(f"Número de dias acima da média: {dias_acima_media}")

-- Questão 4 --
Cálculo percentual de faturamento por estado
# Faturamento por estado
faturamento = {
    "SP": 67836.43,
    "RJ": 36678.66,
    "MG": 29229.88,
    "ES": 27165.48,
    "Outros": 19849.53
}

# Cálculo do total
total_faturamento = sum(faturamento.values())

# Cálculo percentual
percentuais = {estado: (valor / total_faturamento) * 100 for estado, valor in faturamento.items()}

# Exibindo os percentuais
for estado, percentual in percentuais.items():
    print(f"{estado}: {percentual:.2f}%")

-- Questão 5 --
Inversão de caracteres de uma string
def inverter_string(s):
    string_invertida = ""
    for i in range(len(s) - 1, -1, -1):
        string_invertida += s[i]
    return string_invertida

# String previamente definida
string_informada = "Olá, mundo!"
resultado = inverter_string(string_informada)
print(resultado)

