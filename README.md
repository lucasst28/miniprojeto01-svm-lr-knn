# Mini-projeto 01: classificação com métodos tradicionais I

Comparação de SVM (linear e RBF), regressão logística e kNN em duas bases:

- **CDC Diabetes Health Indicators** (OpenML 46841): 253 680 pessoas, 21 atributos, alvo binário (13,9% com diabetes).
- **Mice Protein Expression** (Kaggle): 1 080 medições de 77 proteínas em 72 camundongos, 8 classes.

Disciplina de Aprendizado de Máquina, PPGCO/UFU.

## Conteúdo

| Arquivo | O que tem |
|---|---|
| `cdc.ipynb` | CDC: estatísticas, modelos sem e com `class_weight="balanced"`, matrizes de confusão, bootstrap e McNemar |
| `mice.ipynb` | Mice Protein: divisão por animal, modelos, fronteiras em PCA, controle com divisão ingênua, bootstrap por animal e análise das proteínas |
| `relatorio/relatorio.pdf` | Relatório (fonte em `relatorio/relatorio.tex`, figuras em `relatorio/figuras/`) |

## Como rodar

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

- **CDC:** baixado automaticamente do OpenML na primeira execução (fica salvo em `dados/`).
- **Mice Protein:** baixe `Data_Cortex_Nuclear.csv` do Kaggle (base *Mice Protein Expression*) e coloque em `dados/Data_Cortex_Nuclear.csv`.

Todos os sorteios usam `random_state=42`, então os números saem iguais aos do relatório. O CDC leva cerca de 5 minutos (a maior parte no SVM linear sem pesos).
