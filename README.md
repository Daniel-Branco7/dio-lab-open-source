
## Olá Seja Bem Vindo ao meu perfil!

Me Chamo Daniel, tenho 36 anos, adoro conquistar conhecimentos, ter novos desafios. Atualmente estou me dedicando aos estudos, e buscando uma nova oportunidade no mercado de trabalho.
Conheci a DIO recentemente ofertando os BootCamps que acho fantástico abrir o leque para mais pessoas ter conhecimento e buscar uma qualificação melhor na área de tecnologia pela [Digital Inovation One](https://www.dio.me/).

Vou estudar para conquistar o meu espaço e fazer a diferença na vida das pessoas agregando comprometimento com muita empatia ao próximo.

Adoro jogar nas minhas horas vagas, como [American_Truck_Simulator](https://store.steampowered.com/app/270880/American_Truck_Simulator/) dentre outros.
Estou me dedicando para aprender a cada dia mais e em breve ensinar outras pessoas.



Obrigado e Boa sorte a todos!
## 🔗 Para se conectar comigo no linkedIn
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/daniel-branco/)



## Desafio_1

menu = """

[d] Depositar
[s] Sacar
[e] Extrato 
[q] Sair 

=> """

saldo = 0
limite = 500
extrato = ""
numero_saques = 0
LIMITE_SAQUES = 3

while True:

    opcao = input(menu)

    if opcao =="d":
        valor = float(input("Informe o valor a ser depositado:  "))
        
        if valor >0:
            saldo += valor
            extrato += f"Depósito: R$ {valor:.2f}\n"
        
        else:
            print("Operação Falhou! O valor informado é inválido.")

    
    elif opcao == "s":
        valor = float(input("Informe o valor do Saque: "))

        excedeu_saldo = valor > saldo
        excedeu_limite = valor > limite
        excedeu_saques = numero_saques >= LIMITE_SAQUES 

        if excedeu_saldo:
            print("Operação falhou! Você não tem saldo suficiente.")

        elif excedeu_limite:
            print("Operação falhou! Você não tem limite suficiente.")
        
        elif excedeu_saques:
            print("Operação falhou! Você excedeu o limite diário de Saques.")

        elif valor > 0:
            saldo -= valor
            extrato += f"Saque: R$ {valor:.2f}\n"
            numero_saques += 1


    elif opcao =="e":
        print("\n======== EXTRATO ===========")
        print("Não foram realizadas movimentações." if not extrato else extrato)
        print(f"/nSaldo: R$ {saldo:.2f}")
        print("==============================")
              

    elif opcao =="q":
        break

    else:
        print("Operação Inválida, por favor selecione uma opção válida")
        