    # Faturamento Total

faturamento_total = 0.0

    # Lista de preços e estoque

eventos = {
        "1": ["Cinema", 25.00, 10],
        "2": ["Teatro", 45.00, 10],
        "3": ["Parque de Diversões", 80.00, 10],
        "4": ["Circo", 60.00, 10],
        "5": ["Show", 100.00, 10],
    }

while True:
    
    nome = input("Qual seu nome: ")

    #Validação da idade

    while True:
        try:
            idade = int(input("Qual sua idade: "))
            break
        except ValueError:
            print("Idade inválida! Por favor digite apenas números")

    estudante = input("Você é estudante: (S/N):").lower()

    #Menu de Eventos gerado automaticamente
    print("\nEscolha o evento: ")
    for chave, info in eventos.items():
        print(f"{chave} - {info[0]}")

    evento = input("\nDigite o número do evento: ")

    # Validação do Evento e Estoque
    if evento not in eventos:
        print("Evento inválido")
        continue

    nome_evento, preco, estoque = eventos[evento]
    if estoque == 0:
        print(f"Desculpe, os ingressos para {nome_evento} estão esgotados!")
        continue

    # Categorias e Regras de Desconto
    if idade < 5:
        preco = 0
        categoria = "Criança (gratuito)"
    elif idade <= 12:
        preco = preco * 0.5
        categoria = "Criança (meia entrada)"
    elif idade <= 17:
        preco = preco * 0.5
        categoria = "Adolescente"
    elif idade > 60:
        preco = preco * 0.5
        categoria = "idoso (meia entrada)"
    elif estudante == "s":
        preco = preco * 0.5
        categoria = "Estudante (meia entrada)"
    else:
        categoria = "Adulto (Inteira)"

    # Emissão do Ingresso
    print(f"\n=== INGRESSO ===")
    print(f"Nome: {nome}")
    print(f"Evento: {nome_evento}")
    print(f"Categoria: {categoria}")
    print(f"Preço: R$ {preco:.2f}")
    print(f"================\n")

    # Atualização do Estoque e Caixa

    eventos[evento][2] -= 1
    faturamento_total += preco

    # Condição de parada do sistema
    resposta = input("\n Você deseja comprar outro ingresso? (S/N): ").lower()
    if resposta == "n":
        print("\n===============")
        print("\n Obrigado por usar nosso sistema!")
        print(f"Faturamento Total do Dia: R$ {faturamento_total:.2f}")
        break
