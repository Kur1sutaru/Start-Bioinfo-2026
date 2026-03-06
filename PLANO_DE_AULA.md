# 🗓️ Plano de Aula Detalhado

**Aula:** Python para Bioinformática — Módulo Introdutório  
**Duração:** 3 horas | **Modalidade:** Online | **Plataforma:** Google Colab

---

## ⏱️ 18:00 – 18:40 | BLOCO 1: Parte Conceitual (40 min)

### Objetivos do bloco
- Apresentar o ambiente Colab
- Introduzir tipos de dados, variáveis, listas, dicionários e funções com exemplos biológicos

### Estrutura

| Tempo | Atividade | Recurso |
|---|---|---|
| 18:00 – 18:05 | Boas-vindas, verificação técnica (Colab aberto?) | — |
| 18:05 – 18:15 | Por que Python em bioinformática? Panorama da área | Slides / chat |
| 18:15 – 18:30 | Variáveis, tipos, listas e dicionários (exemplos biológicos) | Notebook conceitual |
| 18:30 – 18:40 | Estruturas de controle (`for`, `if`) e funções | Notebook conceitual |

### Perguntas para engajar a turma
- "Alguém já abriu um arquivo FASTA antes? O que vocês viram?"
- "O que vocês acham que um computador precisa saber para contar quantas vezes a letra G aparece numa sequência?"

---

## ⏱️ 18:40 – 19:40 | BLOCO 2: Prática Guiada (60 min)

### Objetivos do bloco
- Aplicar os conceitos ao vivo no Colab
- Resolver problemas biológicos reais com código simples

### Estrutura

| Tempo | Atividade |
|---|---|
| 18:40 – 18:50 | Abrir notebook de prática; executar células de aquecimento |
| 18:50 – 19:10 | Manipulação de strings: complemento reverso, GC content |
| 19:10 – 19:25 | Listas de sequências + dicionário de contagem de bases |
| 19:25 – 19:40 | Parsing manual de FASTA + leitura de erros comuns |

### Notas para o instrutor
- Digitar ao vivo, não copiar/colar — o erro faz parte do aprendizado
- Ao errar, pausar e perguntar: "O que vocês acham que esse erro está dizendo?"
- Incentivar que alunos digitem junto em seus próprios Colabs

---

## ☕ 19:40 – 19:50 | INTERVALO (10 min)

---

## ⏱️ 19:50 – 20:40 | BLOCO 3: Exercício Aplicado (50 min)

### Objetivos do bloco
- Resolver um mini-pipeline com autonomia
- Integrar todos os conceitos da aula

### Estrutura

| Tempo | Atividade |
|---|---|
| 19:50 – 19:55 | Apresentar o enunciado do exercício |
| 19:55 – 20:20 | Alunos trabalham de forma independente (ou em duplas) |
| 20:20 – 20:40 | Correção ao vivo com participação da turma |

### Tarefa do exercício
Dado um conjunto de sequências de DNA em formato FASTA:
1. Calcular o GC content de cada sequência
2. Identificar a sequência mais longa
3. Fazer o complemento reverso da primeira sequência
4. Contar a frequência de cada nucleotídeo em todas as sequências
5. Imprimir um relatório formatado

---

## ⏱️ 20:40 – 21:00 | BLOCO 4: Discussão e Dúvidas (20 min)

### Estrutura

| Tempo | Atividade |
|---|---|
| 20:40 – 20:50 | Revisão dos conceitos-chave (perguntar à turma) |
| 20:50 – 21:00 | Dúvidas abertas + próximos passos |

### Próximos passos sugeridos
- **BioPython** — parsing de FASTA, BLAST, alinhamento
- **pandas** — tabelas de metadados, expressão gênica
- **matplotlib / seaborn** — visualização de dados biológicos
- **Nextflow / Snakemake** — pipelines reprodutíveis

---

## 📌 Materiais necessários (checklist do instrutor)

- [ ] Notebook `02_pratica_guiada.ipynb` aberto no Colab e testado
- [ ] Notebook `03_exercicio_aplicado.ipynb` com células travadas (sem gabarito visível)
- [ ] Link compartilhável dos notebooks (modo leitura no GitHub ou Google Drive)
- [ ] Chat da plataforma de vídeo aberto para dúvidas em tempo real
- [ ] Arquivo FASTA de exemplo preparado (incluído nos notebooks)
