# Conectividade no Brasil: análise do IBC da Anatel (2021–2024)

Análise do **Índice Brasileiro de Conectividade (IBC)** dos 5.570 municípios brasileiros, com dados abertos da Anatel, e um dashboard interativo para explorar o índice por UF e por município.

## Principais achados

Base: 5.570 municípios × 4 anos (2021 a 2024), 22.280 linhas.

1. **A desigualdade regional é grande.** O IBC médio das UFs vai de 33,0 (AM) a 73,3 (DF). Por região, na média de 2021–2024: Sudeste 59,7, Sul 58,6, Centro-Oeste 56,4, Nordeste 46,3 e Norte 40,8.
2. **A fibra é o fator que mais acompanha o IBC.** Correlação de 0,77 entre presença de fibra e IBC, à frente de cobertura 4G/5G (0,67) e densidade de acessos móveis (0,66).
3. **O adensamento de estações (ERBs) tem relação fraca com o IBC** (correlação 0,17), bem menor que a das demais variáveis.
4. **Concentração de mercado (HHI) e IBC andam juntos, não em sentido contrário.** Na média por UF, a correlação do IBC com o HHI é 0,48 (banda larga fixa) e 0,61 (móvel). É uma associação, não prova que a concentração melhore a conectividade.
5. **Há municípios com celular, mas sem fibra.** Em 2024, 438 municípios tinham cobertura 4G/5G de pelo menos 80% e presença de fibra de no máximo 33, o que os torna candidatos a expansão de backhaul. Os estados com mais casos: MG (123), RN (70), PB (49) e PE (31).
6. **Em 2024 a média do IBC não avançou (52,6 em 2023 para 52,4).** Norte e Centro-Oeste caíram. Desde setembro de 2024 a Anatel mudou o limiar de cobertura de −110 para −90 dBm, então a comparação com anos anteriores deve ser feita com cuidado.

Todos os números acima são calculados no final de `src/analise.ipynb`.

## Dados

- Fonte: Anatel, Índice Brasileiro de Conectividade por município ([dados abertos da Anatel](https://www.anatel.gov.br/dadosabertos)). A versão usada aqui vem do arquivo `br_anatel_indice_brasileiro_conectividade_municipio.csv`.
- Colunas principais: `ibc`, `cobertura_pop_4g5g`, `fibra` (0, 50 ou 100), `densidade_smp`, `densidade_scm`, `hhi_smp`, `hhi_scm` e `adensamento_estacoes`.
- O IBC combina densidade de acessos, cobertura 4G/5G, adensamento de estações, presença de fibra e competitividade.

## O que o projeto faz

- Análise exploratória: IBC por UF, evolução ao longo dos anos e correlações.
- Teste de concentração de mercado (HHI) contra o IBC por UF.
- Lista de municípios prioritários para backhaul (pouca fibra, muita cobertura móvel).
- Dashboard interativo (`dashboard_final.ipynb`) com filtros de ano e UF.

## Estrutura

```
projeto_conectividade/
├── data/
│   └── br_anatel_indice_brasileiro_conectividade_municipio.csv
├── src/
│   ├── analise.ipynb
│   └── dashboard_final.ipynb
└── requirements.txt
```

## Como executar

1. `pip install -r requirements.txt`
2. Abra `src/analise.ipynb` ou `src/dashboard_final.ipynb` no Jupyter. Os notebooks leem o CSV em `../data/`, então abra-os a partir da pasta `src/`.
3. Execute as células em ordem.

## Autora

Laura Silva Soares de Melo · [LinkedIn](https://www.linkedin.com/in/laura-soares-313067195) · [GitHub](https://github.com/lssmsilva)

Dados: Anatel. Licença: MIT.
