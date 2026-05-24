# Análise de Risco e Classificação da Severidade de Ocorrências Aeronáuticas Brasileiras

Projeto desenvolvido para a disciplina de Inteligência Artificial II do curso de Engenharia de Computação.

## Objetivo

Analisar a severidade de ocorrências aeronáuticas brasileiras registradas pelo CENIPA/SIPAER, identificando padrões associados a incidentes, incidentes graves e acidentes.

O projeto combina:

- análise exploratória de risco;
- Random Forest para classificação e importância de variáveis;
- Perceptron Multicamadas (MLP) com TensorFlow/Keras;
- comparação de desempenho entre modelos.

## Base de dados

Foram utilizadas três tabelas públicas do CENIPA/SIPAER:

- `ocorrencia.csv`
- `aeronave.csv`
- `ocorrencia_tipo.csv`

As tabelas foram integradas por meio das chaves de ocorrência presentes nos arquivos.

## Definição de severidade

A variável-alvo do projeto é a classificação da ocorrência:

| Classe | Descrição |
|---|---|
| Incidente | Menor severidade |
| Incidente Grave | Severidade intermediária |
| Acidente | Maior severidade |

## Metodologia

O projeto foi dividido nas seguintes etapas:

1. Carregamento e integração dos dados.
2. Criação de variáveis derivadas, como idade da aeronave, faixa de PMD e faixa de horário.
3. Análise de taxa de gravidade por categoria.
4. Treinamento de Random Forest.
5. Treinamento de MLP.
6. Comparação entre os modelos.

## Principais resultados

O Random Forest apresentou melhor desempenho geral que a MLP.

| Modelo | Acurácia | F1-score | Recall Acidente |
|---|---:|---:|---:|
| Random Forest | 0.8588 | 0.8585 | 0.8530 |
| MLP Keras | 0.8164 | 0.8331 | 0.7528 |

## Principais conclusões

A análise indicou que a severidade das ocorrências varia de forma relevante conforme:

- tipo de operação;
- fase de operação;
- tipo de ocorrência;
- peso máximo de decolagem da aeronave;
- tipo e quantidade de motores;
- localização geográfica.

Entre os principais achados, operações agrícolas, operações experimentais, aeronaves leves, voo a baixa altura, manobra e perda de controle em voo apresentaram maior proporção de eventos graves dentro das ocorrências registradas.

## Tecnologias utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- TensorFlow/Keras
- Kaggle Notebooks

## Como executar

1. Baixe os arquivos públicos do CENIPA.
2. Crie um dataset no Kaggle contendo:
   - `ocorrencia.csv`
   - `aeronave.csv`
   - `ocorrencia_tipo.csv`
3. Abra o notebook localizado na pasta `notebooks/`.
4. Execute as células em ordem.

## Observação

Os arquivos CSV originais não foram incluídos no repositório para evitar problemas de tamanho e versionamento. O projeto utiliza dados públicos do CENIPA/SIPAER.
