# Python-File-Organizer-Automation
import os
import shutil
from datetime import datetime

# --------------------------------------------
# CONFIGURAÇÃO: coloque o caminho da sua pasta
# --------------------------------------------
PASTA_ALVO = r"C:\Users\SeuUsuario\Downloads"  # alterar aqui

# Tipos de arquivos e suas pastas de destino
TIPOS = {
    "Imagens": [".png", ".jpg", ".jpeg", ".gif"],
    "PDFs": [".pdf"],
    "Documentos": [".docx", ".doc", ".txt"],
    "Planilhas": [".xlsx", ".xls", ".csv"],
    "Vídeos": [".mp4", ".mov", ".avi"],
    "Programas": [".exe", ".msi"],
    "Compactados": [".zip", ".rar", ".7z"],
}

# Criar pasta de logs
os.makedirs("logs", exist_ok=True)

def registrar_log(mensagem):
    """Salva logs das operações realizadas."""
    with open("logs/automacao_log.txt", "a", encoding="utf-8") as log:
        log.write(f"[{datetime.now()}] {mensagem}\n")

def organizar_arquivos():
    """Organiza arquivos conforme os tipos definidos."""
    for arquivo in os.listdir(PASTA_ALVO):
        caminho = os.path.join(PASTA_ALVO, arquivo)

        if os.path.isfile(caminho):
            nome, extensao = os.path.splitext(arquivo)
            extensao = extensao.lower()

            for pasta, extensoes in TIPOS.items():
                if extensao in extensoes:
                    destino = os.path.join(PASTA_ALVO, pasta)
                    os.makedirs(destino, exist_ok=True)

                    novo_caminho = os.path.join(destino, arquivo)
                    shutil.move(caminho, novo_caminho)

                    registrar_log(f"Movido: {arquivo} → {pasta}")
                    print(f"Movido: {arquivo} → {pasta}")
                    break

def renomear_arquivos():
    """Renomeia arquivos adicionando data e um índice."""
    for pasta in TIPOS.keys():
        caminho_pasta = os.path.join(PASTA_ALVO, pasta)

        if os.path.exists(caminho_pasta):
            indice = 1

            for arquivo in os.listdir(caminho_pasta):
                nome, ext = os.path.splitext(arquivo)
                data = datetime.now().strftime("%Y-%m-%d")

                novo_nome = f"{pasta}_{data}_{indice}{ext}"
                indice += 1

                origem = os.path.join(caminho_pasta, arquivo)
                destino = os.path.join(caminho_pasta, novo_nome)

                os.rename(origem, destino)
                registrar_log(f"Renomeado: {arquivo} → {novo_nome}")
                print(f"Renomeado: {arquivo} → {novo_nome}")

# --------------------------------------------
# Execução da automação
# --------------------------------------------
print("🔧 Organizando arquivos...")
organizar_arquivos()

print("\n✏️ Renomeando arquivos...")
renomear_arquivos()

print("\n✅ Automação concluída!")
