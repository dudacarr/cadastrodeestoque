materiais = []
while True:
    print("Menu:")
    print("1. Cadastrar material")
    print("2. Excluir materiais")
    print("3. Lançar/baixa dos materiais")
    print("4. Vizualizar estoque")
    print("5. Sair")

    escolha = input("Escolha uma opção: ")

    if escolha == '1':
        nome = input("Digite o nome do material :") 
        quantidade = int(input("Digite a quantidade do material: "))
        valorUnitario = float(input("Digite o valor unitário do material: "))
        valorTotal = quantidade * valorUnitario
        material = {
            "nome": nome,
            "quantidade": quantidade,
            "valorUnitario": valorUnitario,
            "valorTotal": valorTotal
        }
        materiais.append(material)
        print("Material cadastrado com sucesso!")

    elif escolha == '2':
        excluir = input("Digite o nome do material que deseja excluir: ")
        materiais = [m for m in materiais if m["nome"] != excluir]
        print("Material excluído com sucesso!")

    elif escolha == '3':
        lancar = input("Digite o nome do material que deseja lançar/baixar: ")
        print("Lançamento/baixa realizado com sucesso!")

    elif escolha == '4':
        print("Estoque de materiais:")
        for m in materiais:
            print(f'Nome: {m["nome"]}, Quantidade: {m["quantidade"]}, Valor Unitário: {m["valorUnitario"]}, Valor Total: {m["valorTotal"]}')

    elif escolha == '5':
        print("Saindo do programa...")
        break

    else:
        print("Opção inválida. Tente novamente.")
