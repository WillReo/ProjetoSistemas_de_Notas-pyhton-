def menu_principal():
    print ('\n----------MENU PRINCIPAL--------------------')
    print ('1 - Adicionar nota do aluno')
    print ('2 - Consultar listagem de alunos adicionados')
    print ('3 - Sair')
    print ('--------------------------------------------')

lista_alunos = []

def ad_nota():
    import copy
    nome = str (input ('Digite o nome do aluno:'))
    nota_math = float (input('Digite a nota do aluno em Matemática:'))
    nota_port = float(input('Digite a nota do aluno em Português:'))
    nota_ingles = float (input ('Digite a nota do aluno em Inglês:'))
    nota_historia = float(input('Digite a nota do aluno em História:'))
    nota_geo = float(input('Digite a nota do aluno em Geografia:'))
    nota_ciencia = float(input('Digite a nota do aluno em Ciência:'))
    nota_arte = float(input('Digite a nota do aluno em Arte:'))
    total = nota_math + nota_port + nota_ingles + nota_historia + nota_geo + nota_ciencia
    media = total / 2
    print ('\nNota total do aluno:{}\nMédia do aluno:{}'.format(total, media))

    alunos_ad = {
        'nome': nome,
        'nota em Matemática': nota_math,
        'nota em Português': nota_port,
        'nota em História' : nota_historia,
        'nota em Geografia': nota_geo,
        'nota em Ciência': nota_ciencia,
        'nota em Arte': nota_arte,
        'Total do aluno': total,
        'Media do aluno': media
    }

    lista_alunos.append(copy.deepcopy(alunos_ad))
    print (f'{nome} foi listado com sucesso!')

def listagem_aluno ():

     while True:
        print ('\n********** Listagem de aluno **********')
        print ('1 - Lista de todos os alunos')
        print ('2 - Consultar aluno por nome')
        print ('3 - Voltar ao menu principal')
        print (39 * '*')

        opcao = int (input ('\nDigite a opção desejada:'))

        if opcao == 1:
            if not lista_alunos:
                print ('\nNão encontramos nenhum aluno na listagem')
            for alunos in lista_alunos:
                print (alunos)

        elif opcao == 2:
            nome_aluno = str (input ('\nDigite o nome do aluno desejado:'))
            encontrado = False
            for alunos in lista_alunos:
                print (alunos)
                encontrado = True
                break
            if not encontrado:
                print ('\nO Aluno não existe.')

        elif opcao == 3:
            return

        else:
            print ('\nAlgo deu errado. Tente novamente.')


#PROGRMA PRINCIPAL

while True:
    menu_principal()
    escolha = int (input('\nEscolha uma das opções:'))
    if escolha == 1:
        ad_nota()

    elif escolha == 2:
        listagem_aluno()

    elif escolha == 3:
        print ('\nPrograma encerrando...')
        break

    else:
        print ('\nEssa opção não existe.')
