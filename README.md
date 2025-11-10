# Trabalho de Otimização – Minimização de Energia de Trajetória

Este projeto contém o notebook `trabalho_otimizacao.ipynb`, o relatório em LaTeX/PDF e arquivos auxiliares que mostram como modelar e resolver, com Pyomo e IPOPT, a trajetória de um robô do ponto (0,0) ao ponto (10,10) minimizando o consumo de energia. Além do caso base, o notebook explora variações como checkpoints intermediários, penalizações adicionais e comparação entre “pistas” alternativas.

## Estrutura do diretório

- `trabalho_otimizacao.ipynb` – Notebook principal com modelagem, solução e visualizações.
- `relatorio_otimizacao.tex` / `Relatorio_Otimizacao.pdf` – Relatório técnico.
- `requirements.txt` – Lista mínima de dependências Python (pip).
- `Miniconda3-latest-Windows-x86_64.exe` (opcional) – Instalador utilizado para garantir o IPOPT.
- `.venv/` (opcional) – Ambiente virtual criado localmente.
- Outros arquivos auxiliares (ex.: scripts temporários, animações geradas).

## Pré-requisitos

- Python 3.10 ou superior.
- Pip atualizado (`pip`, `setuptools`, `wheel`).
- Dependências Python listadas em `requirements.txt`:  
  `numpy`, `scipy`, `matplotlib`, `pyomo`, `ply`, `ipykernel`, `fpdf`.
- Solver IPOPT acessível no sistema (instalação recomendada via Miniconda/Conda).

## Configurando o ambiente

1. **Instalar dependências Python**  
   No terminal (PowerShell/CMD):
   ```bash
   python -m pip install --upgrade pip setuptools wheel
   python -m pip install -r requirements.txt
   ```
   A primeira célula do notebook também executa esse processo; se algum pacote falhar, ela tenta instalá-lo individualmente e emite avisos.

2. **Instalar o IPOPT via Conda (recomendado)**  
   ```bash
   conda install -y -c conda-forge ipopt
   ```
   Por padrão, o notebook aponta para `C:\Users\<usuario>\miniconda3\Library\bin\ipopt.exe`. Caso o executável esteja em outro local, ajuste a variável `ipopt_exec` na célula onde o solver é criado, por exemplo:
   ```python
   ipopt_exec = Path(r'C:\caminho\para\ipopt.exe')
   ```
   Em Linux/macOS, garanta que o binário `ipopt` esteja no PATH ou forneça o caminho absoluto correto.

## Executando o notebook

1. Abra o diretório no Jupyter Notebook ou JupyterLab.
2. Execute as células em ordem:
   - Preparação do ambiente (instalação de dependências).
   - Modelagem e solução do caso base com IPOPT.
   - Células de visualização (gráficos e animações).
   - Seções de experimentos extras (sensibilidade em N, checkpoints, penalização, biblioteca de pistas).
3. Caso o IPOPT não seja encontrado, ajuste o caminho ou instale o solver antes de prosseguir.

***Seguindo esses passos, qualquer usuário com Python e Conda conseguirá reproduzir os resultados do notebook e do relatório.***

