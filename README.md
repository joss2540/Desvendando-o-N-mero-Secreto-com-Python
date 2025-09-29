import random

print("Bem-vindo ao jogo de adivinhação!")
print("Tente adivinhar o número secreto entre 1 e 100.")

numero_secreto = random.randint(1, 100)
tentativas = 0

while True:
    palpite = input("Digite seu palpite: ")

    if not palpite.isdigit():
        print("Por favor, digite um número válido.")
        continue

    palpite = int(palpite)
    tentativas += 1

    if palpite < numero_secreto:
        print("Muito baixo. Tente novamente.")
    elif palpite > numero_secreto:
        print("Muito alto. Tente novamente.")
    else:
        print(f"Parabéns! Você acertou o número em {tentativas} tentativas.")
        break
