# 🧬 Aula 1 — Conceitos Básicos de Python para Bioinformática

> Material de referência para o Bloco 1 (18:00 – 18:40)  
> Execute os exemplos no [Google Colab](https://colab.research.google.com/)

---

## 1. Por que Python em Bioinformática?

Python é hoje a linguagem mais usada em bioinformática porque:

- É **legível** — o código se parece com inglês
- Tem **bibliotecas poderosas**: BioPython, pandas, NumPy, scikit-learn
- É **gratuito e open source**
- Tem uma **comunidade enorme** — sempre tem alguém que já resolveu seu problema

Ferramentas que você vai encontrar no dia a dia e são escritas em Python:
`Scanpy`, `DESeq2 (wrappers)`, `STAR`, scripts de pipeline, análise de scRNA-seq...

---

## 2. Google Colab — Seu ambiente de trabalho

O Colab é um notebook interativo que roda no navegador.  
Não precisa instalar nada. Basta ter uma conta Google.

**Tipos de célula:**
- 🟦 **Célula de código** — onde você escreve Python
- 📝 **Célula de texto** — onde você escreve anotações em Markdown

**Atalhos essenciais:**
| Ação | Atalho |
|---|---|
| Executar célula | `Shift + Enter` |
| Nova célula abaixo | `Ctrl + M, B` |
| Nova célula de texto | `Ctrl + M, M` |

```python
# Seu primeiro código — execute com Shift+Enter!
print("Hello, DNA! 🧬")
```

---

## 3. Variáveis e Tipos de Dados

Uma **variável** é como um rótulo colado a um dado.

```python
# Exemplos com contexto biológico

gene = "BRCA1"                  # str  — texto/sequência
posicao_inicio = 43044295       # int  — número inteiro (posição genômica)
gc_content = 0.587              # float — número decimal
eh_oncogene = True              # bool  — verdadeiro/falso

print(gene)
print(type(gc_content))         # mostra o tipo da variável
```

### Strings — o tipo mais importante para sequências

```python
sequencia = "ATGCGATCGATCGATCG"

# Comprimento
print(len(sequencia))           # 17

# Acessar uma posição (índice começa em 0!)
print(sequencia[0])             # A
print(sequencia[-1])            # G  (último elemento)

# Fatiamento (slicing)
print(sequencia[0:3])           # ATG  (primeiro códon)
print(sequencia[3:6])           # CGA  (segundo códon)

# Métodos úteis de string
print(sequencia.upper())        # já está em maiúscula
print(sequencia.count("A"))     # conta quantos A tem
print(sequencia.replace("T", "U"))  # transcrição simples DNA → RNA
```

---

## 4. Listas — guardando múltiplos valores

```python
# Lista de sequências de amostras
amostras = ["ATGCGT", "GCTAGC", "TTAGCA", "AACGTT"]

print(amostras[0])          # ATGCGT (primeira sequência)
print(amostras[-1])         # AACGTT (última)
print(len(amostras))        # 4

# Adicionando e removendo
amostras.append("CCGGAA")
print(amostras)

# Iterando sobre a lista
for seq in amostras:
    print(seq, "— tamanho:", len(seq))
```

---

## 5. Dicionários — chave e valor

Dicionários são perfeitos para tabelas de referência biológica.

```python
# Contagem de nucleotídeos
contagem = {"A": 0, "T": 0, "G": 0, "C": 0}

sequencia = "ATGCGATCGAAT"

for base in sequencia:
    contagem[base] += 1

print(contagem)
# {'A': 4, 'T': 2, 'G': 3, 'C': 3}

# Acessando valores
print("Adeninas:", contagem["A"])
print("Bases:", list(contagem.keys()))
```

```python
# Tabela de códons — um dicionário real de biologia!
codons = {
    "ATG": "Met (início)",
    "TAA": "Stop",
    "TAG": "Stop",
    "TGA": "Stop",
    "GCT": "Ala",
    "CGT": "Arg",
    "TGT": "Cys",
}

primeiro_codon = "ATG"
print(f"O códon {primeiro_codon} codifica: {codons[primeiro_codon]}")
```

---

## 6. Estruturas de Controle

### if / elif / else

```python
gc_content = 0.65

if gc_content > 0.60:
    print("GC content alto — possível CpG island")
elif gc_content > 0.40:
    print("GC content normal")
else:
    print("GC content baixo")
```

### Laço for

```python
sequencias = ["ATGCGT", "GCTAGC", "TTAGCA"]

for i, seq in enumerate(sequencias):
    gc = (seq.count("G") + seq.count("C")) / len(seq)
    print(f"Sequência {i+1}: {seq} | GC = {gc:.1%}")
```

---

## 7. Funções — reuso de código

```python
def calcular_gc(sequencia):
    """
    Calcula o GC content de uma sequência de DNA.
    
    Parâmetro:
        sequencia (str): string com bases A, T, G, C
    
    Retorna:
        float: proporção de G+C (0 a 1)
    """
    sequencia = sequencia.upper()
    gc = sequencia.count("G") + sequencia.count("C")
    return gc / len(sequencia)


# Testando a função
print(calcular_gc("ATGCGC"))      # 0.6666...
print(calcular_gc("AAAATT"))      # 0.0
print(calcular_gc("GCGCGCGC"))    # 1.0
```

```python
def complemento_reverso(sequencia):
    """
    Retorna o complemento reverso de uma sequência de DNA.
    """
    complemento = {"A": "T", "T": "A", "G": "C", "C": "G"}
    seq = sequencia.upper()
    comp = "".join(complemento[base] for base in seq)
    return comp[::-1]  # inverte a string


print(complemento_reverso("ATGCGT"))   # ACGCAT
```

---

## 8. Leitura de Erros Comuns

Não entre em pânico com erros! Eles são informativos.

```python
# SyntaxError — erro de escrita do código
# print("Hello"   ← falta o parêntese de fechamento

# NameError — variável não definida
# print(sequencia_errada)  ← se a variável não existe

# IndexError — índice fora do intervalo
seq = "ATG"
# print(seq[10])  ← a sequência tem só 3 bases (índices 0,1,2)

# KeyError — chave não existe no dicionário
dic = {"A": 1, "T": 2}
# print(dic["G"])  ← "G" não está nesse dicionário
```

**Dica:** Sempre leia a última linha do erro — ela diz exatamente o que aconteceu e em qual linha.

---

## ✅ Resumo do Bloco 1

| Conceito | Exemplo biológico |
|---|---|
| `str` | Sequência de DNA/RNA |
| `int` / `float` | Posição genômica, GC content |
| `list` | Lista de amostras, sequências |
| `dict` | Tabela de códons, contagem de bases |
| `for` | Iterar sobre sequências |
| `if/else` | Classificar sequências por GC content |
| `def` | Função para calcular GC, complemento reverso |

---

> ➡️ Próximo: [Prática Guiada no Colab](../aulas/02_pratica_guiada.ipynb)
