menu = [
    "1. Cadastrar aluno",
    "2. Listar alunos",
    "3. Buscar aluno por nome",
    "4. Remover aluno",
    "5. Mostar media geral das notas dos alunos",
    "6. Sair"
]
print("\n".join(menu))
alunos = []
def cadastrar_aluno():
    nome = input("Digite o nome do aluno:")
    idade = int(input("Digite a idade do aluno:"))
    nota = float(input("Digite a nota do aluno (0-10):"))
    alunos.append({
        "nome": nome,
        "idade": idade,
        "nota": nota
    })
def listar_alunos():
    if not alunos:
        print("Nenhum aluno cadastrado.")
    else:
        for aluno in alunos:
            print(f"\nNome: {aluno['nome']}, \nIdade: {aluno['idade']}, \nNota: {aluno['nota']}")
def buscar_aluno():
    nome = input("Digite o nome do aluno que deseja buscar:")
    for aluno in alunos:
        if aluno['nome'].lower() == nome.lower():
            print(f"\nNome: {aluno['nome']}, \nIdade: {aluno['idade']}, \nNota: {aluno['nota']}")
            return
    print("Aluno não encontrado.")
def remover_aluno():
    nome = input("Digite o nome do aluno que deseja remover:")
    for aluno in alunos:
        if aluno['nome'].lower() == nome.lower():
            alunos.remove(aluno)
            print("Aluno removido com sucesso.")
            return
    print("Aluno não encontrado.")
def media_geral():
    if not alunos:
        print("Nenhum aluno cadastrado.")
    else:
        media = sum(aluno['nota'] for aluno in alunos) / len(alunos)
        print(f"A média geral das notas dos alunos é: {media:.2f}")
while True:
    opção = int(input("Digite a opção:"))
    if opção == 1:
        cadastrar_aluno()
    elif opção == 2:
        listar_alunos()
    elif opção == 3:
        buscar_aluno()
    elif opção == 4:
        remover_aluno()
    elif opção == 5:
        media_geral()
    elif opção == 6:
        print("Saindo do programa...")
        break
    else:
        print("Opção Invalida")
    
