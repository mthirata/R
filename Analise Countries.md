---
title: "Trabalho Final"
author: "Rodrigo Domingos Allan Feliph Marcelo Hirata"
date: "Friday, May 08, 2015"
output:
  html_document:
    highlight: tango
    theme: journal
  pdf_document: default
  word_document: default
---

Análise dos paises integrantes do G8

G8 é um grupo internacional que reúne os oito paí­ses mais industrializados e desenvolvidos economicamente do mundo. 

Filtro dos paises integrantes do G8

```{r}
library("gcookbook")

paises_G8 <- subset(countries, Name %in% c("United States","Canada","Japan","Germany","France","Italy","United Kingdom","Russian Federation"))

tipos <- factor(c("United States","Canada","Japan","Germany","France","Italy","United Kingdom","Russian Federation"))

```

Análise da dispersão baseado no PIB vs Valor gasto com saúde

```{r}
plot(paises_G8$GDP, paises_G8$healthexp, pch=as.integer(tipos), xlab="PIB (Produto Interno Bruto)",ylab="Gastos com saúde")

legend("topleft", levels(tipos),pch=1:length(levels(tipos)))

title("Geral: PIB x gastos com saúde")


```

Análise da correlação entre PIB vs valor gasto com saúde


```{r}
cor.test(paises_G8$GDP, paises_G8$healthexp)
```


Análise da dispersão baseado no PIB vs Indice Mortalidade Infantil

```{r}
paises <- factor(paises_G8$Name)

plot(paises_G8$GDP, paises_G8$infmortality, 
     xlab="PIB (Produto Interno Bruto)", 
     ylab="Indice Mortalidade Infantil para cada 1000 nascimentos", 
     pch=as.integer(paises))

title("Geral: PIB x Indice de Mortalidade Infantil")

legend("topright", levels(paises),pch=1:length(levels(paises)))
```

Análise da correlação entre PIB vs Indice Mortalidade Infantil

```{r}
cor.test(paises_G8$GDP, paises_G8$infmortality)
```
aaaaaaa
