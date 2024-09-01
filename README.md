# Solucao-exercicios
# 1.Valor da variável SOMA:
INDICE = 13
SOMA = 0
K = 0

while K < INDICE:
    K = K + 1
    SOMA = SOMA + K

print(SOMA)

# 2.Verificar se um número pertence à sequência de Fibonacci:
def is_fibonacci(num):
    a, b = 0, 1
    while a <= num:
        if a == num:
            return True
        a, b = b, a + b
    return False

# Teste com um número (substitua pelo número que deseja testar)
numero = 21
if is_fibonacci(numero):
    print(f"O número {numero} pertence à sequência de Fibonacci.")
else:
    print(f"O número {numero} NÃO pertence à sequência de Fibonacci.")

  # 3.Faturamento diário de uma distribuidora:
import json

# Suponha que este seja o conteúdo do arquivo JSON
faturamento_json = """
{
    "faturamento_diario": [1000, 2000, 0, 3000, 2500, 0, 5000, 4000, 0, 7000, 6000, 0, 0, 0]
}
"""

faturamento_data = json.loads(faturamento_json)
faturamento_diario = faturamento_data['faturamento_diario']

# Filtra dias com faturamento > 0
faturamento_valido = [x for x in faturamento_diario if x > 0]

menor_faturamento = min(faturamento_valido)
maior_faturamento = max(faturamento_valido)
media_faturamento = sum(faturamento_valido) / len(faturamento_valido)

dias_acima_da_media = sum(1 for x in faturamento_valido if x > media_faturamento)

print(f"Menor faturamento: R${menor_faturamento}")
print(f"Maior faturamento: R${maior_faturamento}")
print(f"Dias com faturamento acima da média: {dias_acima_da_media}")

# 4.Percentual de faturamento por estado:
faturamento_estados = {
    "SP": 67836.43,
    "RJ": 36678.66,
    "MG": 29229.88,
    "ES": 27165.48,
    "Outros": 19849.53
}

faturamento_total = sum(faturamento_estados.values())

for estado, valor in faturamento_estados.items():
    percentual = (valor / faturamento_total) * 100
    print(f"{estado} - {percentual:.2f}%")

# 5.Inverter os caracteres de uma string sem usar funções prontas:
def inverter_string(s):
    invertida = ""
    for char in s:
        invertida = char + invertida
    return invertida

# Teste com uma string
string_original = "exemplo"
string_invertida = inverter_string(string_original)
print(f"Original: {string_original}")
print(f"Invertida: {string_invertida}")

