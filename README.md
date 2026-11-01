from colorama import init, Fore, Style

# Inicializa o colorama e garante o reset do estilo do terminal
init(autoreset=True)

# 1. Utilizar uma lista para armazenar os níveis ou as mensagens do reservatório
niveis_reservatorio = [
    ("Nível 1", "Muito baixo (crítico)", "Vermelho"),
    ("Nível 2", "Baixo", "Amarelo"),
    ("Nível 3", "Médio", "Verde"),
    ("Nível 4", "Alto", "Ciano"),
    ("Nível 5", "Muito alto (alerta)", "Azul")
]

# 3. Criar uma função responsável por definir a cor da mensagem conforme o nível informado
def obter_cor_nivel(nivel):
    if nivel == "Nível 1":
        return Fore.RED
    elif nivel == "Nível 2":
        return Fore.YELLOW
    elif nivel == "Nível 3":
        return Fore.GREEN
    elif nivel == "Nível 4":
        return Fore.CYAN
    elif nivel == "Nível 5":
        return Fore.BLUE
    else:
        return Style.RESET_ALL

# 4. Exibir no terminal a situação atual do reservatório com a cor correspondente, traços e tabela
def simular_monitoramento():
    # Traços e Cabeçalho da Tabela
    print("-" * 65)
    print(f"{'NÍVEL DO RESERVATÓRIO':<22} | {'SITUAÇÃO':<25} | {'COR'}")
    print("-" * 65)
    
    # Percorrendo a lista para exibir os dados
    for item in niveis_reservatorio:
        nivel = item[0]
        situacao = item[1]
        nome_cor = item[2]
        
        # Obtém a cor correspondente através da função
        cor_selecionada = obter_cor_nivel(nivel)
        
        # 4 & 5. Exibição colorida no terminal e restauração automática do estilo padrão
        linha = f"{nivel:<22} | {situacao:<25} | {nome_cor}"
        print(cor_selecionada + linha + Style.RESET_ALL)
        
    print("-" * 65)
    print("Simulação concluída com sucesso. Estilo padrão restaurado.")

# Execução da simulação
if __name__ == "__main__":
    simular_monitoramento()
