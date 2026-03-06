# ✅ Gabarito — Exercício Aplicado

> **Atenção:** Tente resolver por conta própria antes de consultar este gabarito!

---

## Configuração inicial

```python
fasta_dados = """...mesmo texto do exercício..."""

# Execute as funções auxiliares do notebook do exercício

seqs = parsear_fasta(fasta_dados)
```

---

## Tarefa 1 — Parse do FASTA

```python
seqs = parsear_fasta(fasta_dados)

print(f"Total de sequências: {len(seqs)}\n")

for header, seq in seqs.items():
    nome = header.split('|')[0]  # pega só o nome do gene
    print(f"{nome:10} | {len(seq)} bp")
```

**Saída esperada:**
```
Total de sequências: 5

TRPV1      | 160 bp
TRPA1      | 222 bp
PIEZO2     | 180 bp
IL6        | 160 bp
NGF        | 160 bp
```

---

## Tarefa 2 — GC Content

```python
print("Gene       | GC Content | Classificação")
print("-" * 45)

for header, seq in seqs.items():
    nome = header.split('|')[0]
    gc = calcular_gc(seq)

    if gc > 0.60:
        classe = "alto"
    elif gc >= 0.40:
        classe = "normal"
    else:
        classe = "baixo"

    print(f"{nome:10} | {gc:.1%}      | {classe}")
```

---

## Tarefa 3 — Sequência mais longa

```python
maior_tamanho = 0
seq_mais_longa = ""

for header, seq in seqs.items():
    if len(seq) > maior_tamanho:
        maior_tamanho = len(seq)
        seq_mais_longa = header.split('|')[0]

print(f"Sequência mais longa: {seq_mais_longa} ({maior_tamanho} bp)")
```

**Saída esperada:** `Sequência mais longa: TRPA1 (222 bp)`

---

## Tarefa 4 — Complemento reverso

```python
# Pega a primeira sequência (TRPV1)
primeira_seq = list(seqs.values())[0]
primeiro_header = list(seqs.keys())[0].split('|')[0]

comp_rev = complemento_reverso(primeira_seq)

print(f"Gene: {primeiro_header}")
print(f"Original ({len(primeira_seq)} bp):  {primeira_seq[:30]}...")
print(f"Comp. rev. ({len(comp_rev)} bp): {comp_rev[:30]}...")
print(f"\nTamanhos iguais? {len(primeira_seq) == len(comp_rev)}")
```

---

## Tarefa 5 — Relatório Final

```python
# Calcula os valores necessários
gc_values = [calcular_gc(seq) for seq in seqs.values()]
gc_medio = sum(gc_values) / len(gc_values)

tamanhos = {header.split('|')[0]: len(seq) for header, seq in seqs.items()}
mais_longa = max(tamanhos, key=tamanhos.get)
mais_curta = min(tamanhos, key=tamanhos.get)

print("=" * 40)
print("       RELATÓRIO DE ANÁLISE FASTA       ")
print("=" * 40)
print(f"Total de sequências:    {len(seqs)}")
print(f"GC content médio:       {gc_medio:.1%}")
print(f"Sequência mais longa:   {mais_longa} ({tamanhos[mais_longa]} bp)")
print(f"Sequência mais curta:   {mais_curta} ({tamanhos[mais_curta]} bp)")
print("=" * 40)
```

**Saída esperada:**
```
========================================
       RELATÓRIO DE ANÁLISE FASTA       
========================================
Total de sequências:    5
GC content médio:       57.8%
Sequência mais longa:   TRPA1 (222 bp)
Sequência mais curta:   TRPV1 (160 bp)
========================================
```

---

## BÔNUS — Contagem global de nucleotídeos

```python
contagem_total = {'A': 0, 'T': 0, 'G': 0, 'C': 0}

for seq in seqs.values():
    seq = seq.upper()
    for base in ['A', 'T', 'G', 'C']:
        contagem_total[base] += seq.count(base)

total_bases = sum(contagem_total.values())

print("Contagem global de nucleotídeos:")
print("-" * 30)
for base, count in contagem_total.items():
    barra = '█' * (count // 10)
    print(f"  {base}: {count:4d} ({count/total_bases:.1%})  {barra}")
```

**Saída esperada:**
```
Contagem global de nucleotídeos:
------------------------------
  A:  194 (22.0%)  ███████████████████
  T:  145 (16.4%)  ██████████████
  G:  323 (36.5%)  ████████████████████████████████
  C:  221 (25.0%)  ██████████████████████
```

---

## 💡 O que você acabou de construir

Este mini-pipeline, mesmo sendo simples, já replica a lógica de ferramentas de bioinformática reais:

1. **Leitura de dados** (parse FASTA) → como `Bio.SeqIO.parse()`
2. **Análise de qualidade** (GC content, tamanho) → como `FastQC`
3. **Transformação** (complemento reverso) → como `samtools revcomp`
4. **Relatório** → como saídas de pipelines Nextflow/Snakemake

Parabéns por completar o exercício! 🎉
