# Análise de Saúde de Estoque — Período de Alta Demanda (set–jan)

> Dashboard analítico de estoque nacional construído do zero: ETL, modelagem de dados e Power BI.
> Projeto autoral bases geradas, tratadas e modeladas por mim.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=flat&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)

---

## Contexto de negócio

Na logística, saber a saúde do estoque é crítico. Este projeto simula um cenário real:
uma empresa que adquiriu estoque **acima da média** antes do período de pico (set–jan)
para evitar ruptura — e analisa se essa decisão gerou gargalos ou ganhos operacionais.

**Pergunta central:** comprar over-stock antes do pico gera retorno ou problema?

---

## O que o dashboard responde

- Como está a distribuição da curva ABC do estoque?
- Qual o giro de estoque mês a mês e seu custo associado?
- Houve melhoria ou deterioração no controle de inventário ao longo do período?
- Onde estão as maiores e menores vendas por categoria?

---

## Arquitetura do projeto

```
Bases brutas (xlsx)
    │
    ▼
ETL — Excel + Power Query (M)
    │  limpeza · padronização · nomenclatura · governança
    ▼
Modelagem — Star Schema no Power BI
    │  2 tabelas fato (vendas + estoque) · N dimensões
    ▼
Medidas DAX (organizadas em pastas por contexto)
    │
    ▼
Dashboard final
```

---

## Principais insights

### Curva ABC
A distribuição obtida foge do padrão esperado, indicando concentração irregular no grupo A
e necessidade de revisão das políticas de reposição e priorização de SKUs.

### Giro x Custo
Entre setembro e dezembro houve crescimento significativo no giro com redução no custo total
do estoque movimento que sugere ganho operacional real no período de pico.

### Lucro x Margem
Os valores de lucro ainda não incorporam descontos comerciais dos primeiros meses,
reforçando a importância de integrar dados logísticos e financeiros para visão de margem real.

---

## Tecnologias utilizadas

| Ferramenta | Finalidade |
|---|---|
| Excel + Power Query (M) | ETL: ingestão, limpeza, normalização |
| Power BI (DAX) | Modelagem, medidas e dashboard final |
| SQL | Análises exploratórias e validação |
| ChatGPT / Claude / DeepSeek | Geração das bases fictícias e revisão estrutural |

---
## Imagens do projeto

<img width="1917" height="1018" src="OneDrive/Área de Trabalho/GitImagens/alerta_do_excel_setembro.png"/>

<img width="250" height="250" src="OneDrive/Área de Trabalho/GitImagens/Medidas.png"/>

<img width="250" height="1000" src="OneDrive/Área de Trabalho/GitImagens/Medidas_estoque.png"/>

<img width="1917" height="1018" src="OneDrive/Área de Trabalho/GitImagens/relacionamentos.png"/>

I<img width="1917" height="1018" src="OneDrive/Área de Trabalho/GitImagens/relacionamentos_1_pra muitos.png"/>

<img width="1917" height="1018" src="OneDrive/Área de Trabalho/GitImagens/dashboard_inicial.jpg"/>

<img width="1917" height="1018" src="OneDrive/Área de Trabalho/GitImagens/Imagem_tooltips_giro.png"/>

<img width="1917" height="1018" src="OneDrive/Área de Trabalho/GitImagens/imagem_tooltips_soma_do_estoque.png"/>


## Estrutura do repositório

```
/bases          → arquivos xlsx tratados (estoque + vendas set–jan)
/imagens        → capturas do dashboard e modelagem
README.md       → este documento
```

---

## Próximos passos

- [ ] Publicar dashboard no Power BI Service (link público)
- [ ] Adicionar análise SQL complementar
- [ ] Expandir para modelo preditivo de demanda

---

**Bruna Karine** · [LinkedIn](https://www.linkedin.com/in/brunakarine/) · [GitHub](https://github.com/BrunaKarineVEB)
