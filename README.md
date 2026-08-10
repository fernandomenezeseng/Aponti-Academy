# Aponti-Academy
# Aponti Academy — Análise de Dados

Repositório de estudos e projetos práticos do curso de **Análise de Dados da Aponti**, reunindo exercícios de módulo e o projeto principal de análise dos dados abertos de acidentes de trânsito da **Polícia Rodoviária Federal (PRF)**.

## Autor

Fernando José Menezes da Silva

## Sumário

- [Sobre o repositório](#sobre-o-repositório)
- [Conteúdo](#conteúdo)
- [Projeto principal — Análise PRF 2025](#projeto-principal--análise-prf-2025)
- [Materiais de módulo](#materiais-de-módulo)
- [Como executar](#como-executar)
- [Requisitos](#requisitos)

## Sobre o repositório

Este repositório reúne os artefatos produzidos ao longo da trilha de Análise de Dados da Aponti, incluindo notebooks de tratamento e exploração de dados, planilhas de atividades e exercícios de módulo. Serve tanto como portfólio de aprendizado quanto como base para os projetos práticos do curso.

## Conteúdo

| Arquivo | Descrição |
|---|---|
| [`analise_prf_2025.ipynb`](https://github.com/user-attachments/files/30915731/analise_prf_2025.ipynb) | Notebook principal: preparação, limpeza e transformação dos dados de acidentes da PRF 2025. |
| [`dados_abertos_prf_atividade.xlsx`](https://github.com/user-attachments/files/30915962/dados_abertos_prf_atividade.xlsx) | Planilha de apoio com os dados abertos da PRF utilizados na atividade prática. |
| [`Modulo_02_PRF_fernandoMenezes.xls`](https://github.com/user-attachments/files/30915955/Modulo_02_PRF_fernandoMenezes.xls) | Exercício do Módulo 2 do curso, com análise inicial sobre os dados da PRF. |

## Projeto principal — Análise PRF 2025

O notebook `analise_prf_2025.ipynb` transforma o dado bruto de acidentes de trânsito em rodovias federais (72.529 registros) em duas bases de saída:

- **Base analítica** — completa, para EDA e dashboards (Power BI);
- **Base modelável** — reduzida e livre de *data leakage*, pronta para treinar um modelo de árvore de decisão explicável.

### Etapas do pipeline

1. Ingestão e padronização de nomes de colunas;
2. Diagnóstico de qualidade (tipos, nulos, cardinalidade);
3. Conversão de colunas numéricas e temporais;
4. Criação de variáveis derivadas (`turno`, `faixa_horaria`, `br_formatada`, `chave_localidade`);
5. Tratamento de valores ausentes (categóricos → `IGNORADO`, contagens → `0`);
6. Construção da variável-alvo `acidente_fatal` (`1` quando `mortos >= 1`) e de indicadores de gravidade;
7. Checagem automática contra vazamento de dados (*data leakage*) na base modelável;
8. Exportação das bases tratadas, do dicionário de variáveis e do log de decisões de tratamento.

### Principais números

- **72.529** acidentes analisados;
- **5.210** acidentes fatais (**taxa de fatalidade ≈ 7,18%**);
- **6.043** mortos e **83.550** feridos no total;
- Base analítica final com **44 colunas**; base modelável com **19 colunas**.

## Materiais de módulo

Os arquivos `dados_abertos_prf_atividade.xlsx` e `Modulo_02_PRF_fernandoMenezes.xls` correspondem a atividades práticas de módulos anteriores do curso, utilizados como base ou etapa preparatória para o projeto principal de análise da PRF.

## Como executar

1. Clone o repositório:
   ```bash
   git clone https://github.com/fernandomenezeseng/Aponti-Academy.git
   ```
2. Abra `analise_prf_2025.ipynb` no Jupyter, VS Code ou Google Colab.
3. Coloque o CSV de dados abertos da PRF na pasta `dados_brutos/` (criada automaticamente pelo notebook, caso não exista).
4. Execute as células em ordem — as bases tratadas e os artefatos de apoio serão gerados em `dados_tratados/` e `logs/`.

> O notebook foi originalmente desenvolvido no Google Colab. Ao rodar localmente, substitua as células de upload via `google.colab.files` pelo carregamento direto do arquivo.

## Requisitos

- Python 3.9+
- pandas
- numpy
- matplotlib

```bash
pip install pandas numpy matplotlib
```

---

*Repositório mantido como parte da trilha de Análise de Dados da Aponti.*

[analise_prf_2025.ipynb](https://github.com/user-attachments/files/30915731/analise_prf_2025.ipynb)

[dados_abertos_prf_atividade.xlsx](https://github.com/user-attachments/files/30915962/dados_abertos_prf_atividade.xlsx)

[Modulo_02_PRF_fernandoMenezes.xls](https://github.com/user-attachments/files/30915955/Modulo_02_PRF_fernandoMenezes.xls)



