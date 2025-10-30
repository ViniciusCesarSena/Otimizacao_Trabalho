# Trabalho de Otimizacao - Minimizacao de Energia de Trajetoria

Este projeto apresenta um notebook (`trabalho_otimizacao.ipynb`) que demonstra como formular e resolver, com Pyomo e IPOPT, o problema de minimizar a energia consumida por um robo que percorre um plano entre os pontos (0,0) e (10,10). A energia e aproximada via integracao trapezoidal do termo `v(t)^2 + sin(t)`. Alem do caso base, o notebook inclui experimentos extras com diferentes discretizacoes, restricoes personalizadas, biblioteca de “pistas” (cenarios de trajeto) e uma animacao da trajetoria escolhida como mais eficiente.

## Estrutura

- `trabalho_otimizacao.ipynb` – Notebook principal, organizado em:
  - Preparacao do ambiente e importacao de bibliotecas.
  - Modelagem Pyomo do problema original.
  - Resolucao com IPOPT e avaliacao grafica.
  - Experimentos extras:
    - Sensibilidade ao numero de intervalos.
    - Checkpoint intermediario obrigatório.
    - Funcao objetivo com penalizacao adicional.
  - Biblioteca de pistas personalizadas (linha direta, checkpoint central, corredor guiado) e comparacao de resultados.
  - Animacao da melhor trajetoria encontrada.
- `Relatorio_Otimizacao.pdf` – Relatorio tecnico (PDF) com descricao do problema, formulacao, justificativa do solver e analise dos resultados.
- `Miniconda3-latest-Windows-x86_64.exe` – Instalador usado para disponibilizar o solver IPOPT (mantido caso seja necessario reinstalar).
- `.venv/` (opcional) – Ambiente virtual local criado pelo usuario.

## Pre-requisitos

- Python 3.10 ou superior.
- Pip atualizado (`pip`, `setuptools`, `wheel`).
- Pacotes Python: `numpy`, `scipy`, `matplotlib`, `pyomo`.
- Solver IPOPT disponivel (recomendado: instalacao via Miniconda).

## Preparando o ambiente

1. **Dependencias via pip**  
   A primeira celula do notebook automatiza esta etapa chamando `pip install -r requirements.txt`, mas e possivel executar manualmente:
   ```bash
   python -m pip install --upgrade pip setuptools wheel
   python -m pip install -r requirements.txt
   ```

2. **Instalando o IPOPT**  
   Com Miniconda:
   ```bash
   conda install -y -c conda-forge ipopt
   ```
   O notebook aponta para `C:\Users\<usuario>\miniconda3\Library\bin\ipopt.exe`. Ajuste a variavel `ipopt_exec` se o solver estiver em outro local.

## Executando o notebook

1. Abra o diretorio `Otimizacao_Trabalho` no Jupyter Notebook ou JupyterLab.
2. Execute as celulas na ordem em que aparecem:
   - Preparacao do ambiente.
   - Modelagem Pyomo do caso base.
   - Resolucao com IPOPT e graficos iniciais.
   - Se desejado, rode as seções “Experimentos extras” e “Biblioteca de pistas personalizadas” para comparar cenarios.
   - A ultima seção gera uma animacao da trajetoria mais eficiente encontrada (requer que os cenarios tenham sido executados antes).

## Exploracoes adicionais

- **Sensibilidade em N** – Avalia como o refinamento da discretizacao altera a energia e a trajetoria.
- **Checkpoint intermediario** – Simula missao que exige visitar um ponto especifico no meio do percurso.
- **Penalizacao alternativa** – Ajusta a funcao objetivo para privilegiar aproximacao progressiva ao destino.
- **Pistas personalizadas** – Permite comparar automaticamente diferentes configuracoes de restricoes, mostrando energia, condicao do solver e graficos sobrepostos.
- **Animacao** – Gera uma visualizacao dinamica do caminho selecionado como melhor.

## Sugestoes de uso

- Rodar o notebook por completo quando for apresentar resultados, garantindo que as figuras e animacoes estejam atualizadas.
- Exportar graficos ou capturas de tela das pistas e da animacao para incluir em relatorios ou apresentações.
- Ajustar peso de penalizacoes, posicoes dos checkpoints ou limites do corredor para adaptar o estudo a outros cenarios de navegação.

## Contato

Trabalho desenvolvido por Guilherme Fernandes Monteiro (RA 22403229) para a disciplina de Otimizacao. Qualquer duvida pode ser direcionada ao autor conforme as orientacoes da disciplina.
