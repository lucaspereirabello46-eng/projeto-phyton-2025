# projeto-phyton-2025
projeto criado na linguagem phyton

# Agenda de Contatos - Projeto Iniciante em Python

contatos = []  # lista para armazenar os contatos

def adicionar_contato():
    nome = input("Digite o nome: ")
    telefone = input("Digite o telefone: ")
    email = input("Digite o e-mail: ")
    contato = {"nome": nome, "telefone": telefone, "email": email}
    contatos.append(contato)
    print(f"✅ Contato {nome} adicionado com sucesso!\n")

def listar_contatos():
    if not contatos:
        print("📭 Nenhum contato cadastrado.\n")
        return
    print("📒 Lista de Contatos:")
    for i, contato in enumerate(contatos, 1):
        print(f"{i}. {contato['nome']} - {contato['telefone']} - {contato['email']}")
    print()

def buscar_contato():
    nome = input("Digite o nome para buscar: ")
    for contato in contatos:
        if contato["nome"].lower() == nome.lower():
            print(f"🔎 Encontrado: {contato['nome']} - {contato['telefone']} - {contato['email']}\n")
            return
    print("❌ Contato não encontrado.\n")

def remover_contato():
    nome = input("Digite o nome do contato para remover: ")
    for contato in contatos:
        if contato["nome"].lower() == nome.lower():
            contatos.remove(contato)
            print(f"🗑️ Contato {nome} removido com sucesso!\n")
            return
    print("❌ Contato não encontrado.\n")

def menu():
    while True:
        print("=== 📖 AGENDA DE CONTATOS ===")
        print("1. Adicionar contato")
        print("2. Listar contatos")
        print("3. Buscar contato")
        print("4. Remover contato")
        print("0. Sair")
        opcao = input("Escolha uma opção: ")

        if opcao == "1":
            adicionar_contato()
        elif opcao == "2":
            listar_contatos()
        elif opcao == "3":
            buscar_contato()
        elif opcao == "4":
            remover_contato()
        elif opcao == "0":
            print("👋 Saindo da agenda... Até logo!")
            break
        else:
            print("❌ Opção inválida, tente novamente.\n")

if __name__ == "__main__":
    menu()

