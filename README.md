# Sistema simples de cadastro de usuários

usuarios = []

def cadastrar_usuario():
    nome = input("Digite o nome: ")
    idade = int(input("Digite a idade: "))
    email = input("Digite o email: ")

    usuario = {
        "nome": nome,
        "idade": idade,
        "email": email
    }

    usuarios.append(usuario)
    print("Usuário cadastrado com sucesso!\n")

def listar_usuarios():
    if not usuarios:
        print("Nenhum usuário cadastrado.\n")
        return

    for i, u in enumerate(usuarios, start=1):
        print(f"{i}. Nome: {u['nome']} | Idade: {u['idade']} | Email: {u['email']}")
    print()

def menu():
    while True:
        print("=== MENU ===")
        print("1 - Cadastrar usuário")
        print("2 - Listar usuários")
        print("3 - Sair")

        opcao = input("Escolha uma opção: ")

        if opcao == "1":
            cadastrar_usuario()
        elif opcao == "2":
            listar_usuarios()
        elif opcao == "3":
            print("Encerrando o programa.")
            break
        else:
            print("Opção inválida.\n")

menu()
