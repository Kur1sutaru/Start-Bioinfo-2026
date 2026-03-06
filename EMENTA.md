# 📄 Ementa — Python para Bioinformática: Módulo Introdutório

---

## Identificação

| | |
|---|---|
| **Disciplina/Curso** | Python para Bioinformática — Módulo Introdutório |
| **Modalidade** | Online (síncrono) |
| **Carga horária** | 3 horas |
| **Plataforma** | Google Colab |
| **Público-alvo** | Estudantes de graduação/pós-graduação e pesquisadores iniciando em bioinformática |
| **Pré-requisito** | Nenhum |

---

## Justificativa

Python se tornou a linguagem padrão em bioinformática pela sua legibilidade, vasta coleção de bibliotecas especializadas (BioPython, pandas, NumPy) e forte adoção pela comunidade científica. Esta aula introduz os conceitos fundamentais da linguagem dentro de um contexto biológico desde o primeiro momento, facilitando a motivação e a retenção do conteúdo por parte de estudantes das ciências da vida.

---

## Objetivo Geral

Capacitar o estudante a escrever e executar scripts Python básicos no Google Colab para resolver problemas elementares de bioinformática, desenvolvendo autonomia para avançar em estudos mais aprofundados.

---

## Objetivos Específicos

Ao final da aula, o estudante será capaz de:

1. Compreender o ambiente Google Colab e executar células de código
2. Declarar variáveis e identificar os tipos de dados fundamentais (`str`, `int`, `float`, `bool`)
3. Utilizar estruturas de dados (`list`, `dict`) para armazenar informações biológicas
4. Aplicar estruturas de controle (`if/else`, `for`) em contextos de análise de sequências
5. Criar funções simples e reutilizáveis
6. Manipular strings para operações básicas sobre sequências de DNA/RNA/proteína
7. Ler e interpretar mensagens de erro comuns em Python
8. Executar um mini-pipeline de análise de sequências FASTA de forma independente

---

## Conteúdo Programático

### Bloco 1 — Fundamentos Conceituais (40 min)

1.1 Introdução ao ambiente de programação
- O que é Python e por que usá-lo em bioinformática
- Google Colab: células de código vs. células de texto (Markdown)
- Executando o primeiro código: `print("Hello, DNA!")`

1.2 Variáveis e tipos de dados
- `str` — sequências de DNA, nomes de genes, IDs
- `int` e `float` — posições genômicas, scores, GC content
- `bool` — condições lógicas em análises
- Boas práticas de nomenclatura de variáveis

1.3 Estruturas de dados
- `list` — listas de sequências, amostras, cromossomos
- `dict` — tabela de códons, contagem de nucleotídeos
- Indexação e fatiamento (`slicing`)

1.4 Estruturas de controle
- `if / elif / else`
- Laço `for` — iterando sobre sequências

1.5 Funções
- Definindo funções com `def`
- Parâmetros e retorno de valores
- Reuso de código em análises

---

### Bloco 2 — Prática Guiada (60 min)

2.1 Navegando no Google Colab
- Criando e organizando um notebook

2.2 Manipulação de strings biológicas
- Complemento reverso de sequência de DNA
- Transcrição DNA → RNA
- Contagem de nucleotídeos

2.3 Listas e dicionários aplicados
- Armazenando múltiplas sequências
- Calculando GC content de uma lista de sequências

2.4 Leitura de arquivos FASTA (simulado)
- Parsing manual de formato FASTA com strings multilinhas
- Separando header e sequência

2.5 Introdução à leitura de erros
- `SyntaxError`, `NameError`, `IndexError` — como interpretar e corrigir

---

### Bloco 3 — Exercício Aplicado (50 min)

Mini-pipeline de análise de sequências:
- Dadas N sequências em formato FASTA (fornecidas no notebook)
- Calcular GC content de cada sequência
- Identificar a sequência mais longa
- Traduzir o primeiro códon de cada sequência
- Gerar um relatório resumido em texto

---

### Bloco 4 — Discussão e Dúvidas (20 min)

- Revisão dos conceitos-chave
- Dificuldades comuns no início
- Próximos passos: BioPython, pandas, Nextflow

---

## Metodologia

- Aula expositiva dialogada com exemplos contextualizados em biologia
- Demonstração ao vivo no Google Colab (live coding)
- Exercício prático com resolução assistida
- Discussão em grupo via chat/voz

---

## Avaliação

Participação no exercício aplicado e resolução de pelo menos 3 das 5 tarefas do mini-pipeline.

---

## Recursos Necessários

- Computador ou tablet com navegador atualizado
- Conta Google ativa
- Acesso à internet

---

## Referências Recomendadas

- [Python.org — Tutorial Oficial](https://docs.python.org/3/tutorial/)
- [BioPython Tutorial](https://biopython.org/DIST/docs/tutorial/Tutorial.html)
- [Google Colab — Guia Introdutório](https://colab.research.google.com/notebooks/intro.ipynb)
- Cock, P.J.A. et al. (2009). Biopython: freely available Python tools for computational molecular biology and bioinformatics. *Bioinformatics*, 25(11), 1422–1423.
