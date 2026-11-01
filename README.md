from colorama import init, Fore, Style

# Inicializa o colorama e garante o reset do estilo
init(autoreset=True)

# Lista contendo os 5 níveis de água do reservatório
niveis_reservatorio = [
    ("Nível 1", "Muito baixo (crítico)"),
    ("Nível 2", "Baixo"),
    ("Nível 3", "Médio"),
    ("Nível 4", "Alto"),
    ("Nível 5", "Muito alto (alerta)")
]

# Função responsável por definir a cor da mensagem conforme o nível informado
def verificar_nivel_agua(nivel_nome, situacao):
    if nivel_nome == "Nível 1":
        print(Fore.RED + f"{nivel_nome}: {situacao} - Risco Crítico!" + Style.RESET_ALL)
    elif nivel_nome == "Nível 2":
        print(Fore.YELLOW + f"{nivel_nome}: {situacao} - Atenção." + Style.RESET_ALL)
    elif nivel_nome == "Nível 3":
        print(Fore.GREEN + f"{nivel_nome}: {situacao} - Nível Estável." + Style.RESET_ALL)
    elif nivel_nome == "Nível 4":
        print(Fore.CYAN + f"{nivel_nome}: {situacao} - Nível Elevado." + Style.RESET_ALL)
    elif nivel_nome == "Nível 5":
        print(Fore.BLUE + f"{nivel_nome}: {situacao} - Alerta Máximo!" + Style.RESET_ALL)

# Simulação do sistema exibindo no terminal a situação atual de cada nível
print("=== SIMULAÇÃO DE NÍVEIS DO RESERVATÓRIO ===")
for item in niveis_reservatorio:
    nivel = item[0]
    situacao = item[1]
    verificar_nivel_agua(nivel, situacao)
print("===========================================")
