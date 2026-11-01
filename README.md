# Importação da biblioteca colorama para colorir as saídas no terminal
from colorama import init, Fore, Style

# Inicializa o colorama (autoreset=True ajuda a restaurar o estilo padrão automaticamente após cada print)
init(autoreset=True)

# 1. Utilizar uma lista para armazenar os níveis e suas respectivas situações
# Cada item contém: (Nome do Nível, Descrição da Situação, Cor do Colorama)
niveis_reservatorio = [
    ("Nível 1", "Muito baixo (crítico)", Fore.RED),
    ("Nível 2", "Baixo", Fore.YELLOW),
    ("Nível 3", "Médio", Fore.GREEN),
    ("Nível 4", "Alto", Fore.CYAN),
    ("Nível 5", "Muito alto (alerta)", Fore.BLUE)
]

# 2. Criar uma função responsável por definir a cor e exibir a mensagem
def exibir_alerta(nivel, situacao, cor):
    """
    Exibe no terminal a situação atual do reservatório com a cor correspondente
    e garante o uso do estilo adequado.
    """
    print(f"{cor}[{nivel}] - Situação: {situacao}{Style.RESET_ALL}")

# 3. Simulação do sistema de monitoramento percorrendo a lista
def simular_monitoramento():
    print("=" * 50)
    print("     SISTEMA DE MONITORAMENTO DE RESERVATÓRIO     ")
    print("=" * 50)
    
    # Laço de repetição para percorrer os níveis cadastrados na lista
    for item in niveis_reservatorio:
        nivel = item[0]
        situacao = item[1]
        cor = item[2]
        
        # Chamada da função de exibição com cores
        exibir_alerta(nivel, situacao, cor)
        
    print("=" * 50)
    print("Simulação concluída. Estilo do terminal restaurado.")

# Execução do programa
if __name__ == "__main__":
    simular_monitoramento()
