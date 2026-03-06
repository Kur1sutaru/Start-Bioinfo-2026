# 🔗 Recursos e Próximos Passos

---

## Continuar aprendendo Python

| Recurso | Link | Nível |
|---|---|---|
| Python.org — Tutorial Oficial | https://docs.python.org/pt-br/3/tutorial/ | Iniciante |
| Python para Todos (Coursera/Dr. Chuck) | https://pt.coursera.org/specializations/python | Iniciante |
| Automate the Boring Stuff | https://automatetheboringstuff.com/ | Iniciante–Intermediário |
| Real Python | https://realpython.com | Todos |

---

## Python para Bioinformática

| Recurso | Link | Destaque |
|---|---|---|
| BioPython Tutorial | https://biopython.org/DIST/docs/tutorial/Tutorial.html | Parse FASTA, BLAST, alinhamento |
| Rosalind — Problemas de bioinformática | https://rosalind.info | Aprenda resolvendo desafios |
| Software Carpentry — Genomics | https://datacarpentry.org/genomics-workshop/ | Workshop completo |
| Bioinformatics Algorithms (Coursera) | https://www.coursera.org/learn/bioinformatics | Algoritmos clássicos |

---

## Ferramentas que você vai usar na prática

### Análise de dados biológicos
- **pandas** — tabelas de metadados, expressão gênica → https://pandas.pydata.org/
- **NumPy** — cálculos numéricos → https://numpy.org/
- **matplotlib / seaborn** — visualização → https://seaborn.pydata.org/

### Single-cell RNA-seq
- **Scanpy** — análise de scRNA-seq em Python → https://scanpy.readthedocs.io/
- **AnnData** — formato de dados para single-cell → https://anndata.readthedocs.io/

### Pipelines reprodutíveis
- **Nextflow** → https://www.nextflow.io/
- **Snakemake** → https://snakemake.readthedocs.io/

---

## Comunidades

| Comunidade | Link |
|---|---|
| Bioinformatics Stack Exchange | https://bioinformatics.stackexchange.com/ |
| RSG Brasil (Regional Student Group) | https://rsg-brazil.iscbsc.org/ |
| WB&DS Latin America | https://wbds.la/ |
| Bioconductor Slack | https://bioc-community.herokuapp.com/ |

---

## Google Colab — Dicas rápidas

```python
# Instalar bibliotecas no Colab
!pip install biopython

# Fazer upload de arquivo do seu computador
from google.colab import files
uploaded = files.upload()

# Montar o Google Drive
from google.colab import drive
drive.mount('/content/drive')

# Ver arquivos no diretório atual
import os
os.listdir('.')
```

---

## Próxima aula sugerida

**Módulo 2 — Python Intermediário para Bioinformática:**
- BioPython: parse de GenBank, BLAST programático
- pandas: DataFrames de expressão gênica
- matplotlib: volcano plots, heatmaps
- Introdução a pipelines com Nextflow

---

*Boas análises! 🧬*
