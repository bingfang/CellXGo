---
title: "cellXGene to cellXGo"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```


## Preprocess of single cell data (Best practice, standardize criterial)

## Transfer CellXGene matrix (log_transformed) to Binary matrix

```{}
arr [arr<1] = 0, arr [arr >=1] = 1
# If count >=2 for a gene, the gene is considered as expressed/detected.
```

## Transfer CellXGene matrix to CellTypeXGene

```{}
df.groupby(["cluster"]).mean()
arr[arr>0.5] = 1
# If half of cells in a cell type expressed a gene, the gene was considered as expressed in the cell type
```

## Transfer CellTypeXGene matrix to CellTypeXGo

```{}
import goenrichment
from goenrichment.go import load_gorichdb

goenrich --goenrichDB gene2GO_human.pickle -i query.tsv -o goenrich.tsv
```

## Rank by p-value
Adj P-value
Adjust threshold for go term associated with small number of genes

## Rank by B-score
C program
Go DAG

## Find consensus with NLP/LLM output

