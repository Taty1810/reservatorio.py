from colorama import init, Fore, Style

# Inicializa o Colorama para exibir cores no terminal.
init(autoreset=False)

# Lista com os cinco níveis do reservatório e suas situações.
niveis_reservatorio = [
    {"nivel": 1, "situacao": "Muito baixo (crítico)"},
    {"nivel": 2, "situacao": "Baixo"},
    {"nivel": 3, "situacao": "Médio"},
    {"nivel": 4, "situacao": "Alto"},
    {"nivel": 5, "situacao": "Muito alto (alerta)"}
]


def definir_cor(nivel):
    """Retorna a cor correspondente ao nível do reservatório."""
    cores = {
        1: Fore.RED,     # Vermelho: nível crítico
        2: Fore.YELLOW,  # Amarelo: nível baixo
        3: Fore.GREEN,   # Verde: nível médio
        4: Fore.CYAN,    # Ciano: nível alto
        5: Fore.BLUE     # Azul: nível muito alto
    }
    return cores.get(nivel, Fore.WHITE)


def exibir_situacao(dados):
    """Exibe a situação do reservatório com a cor correspondente."""
    nivel = dados["nivel"]
    situacao = dados["situacao"]
    cor = definir_cor(nivel)

    print(f"{cor}Nível {nivel}: {situacao}{Style.RESET_ALL}")


# Simulação: percorre a lista e exibe os cinco níveis.
print("MONITORAMENTO DO RESERVATÓRIO")
print("-----------------------------")

for item in niveis_reservatorio:
    exibir_situacao(item)

# Garante que o terminal volte ao estilo padrão ao final.
print(Style.RESET_ALL, end="")
