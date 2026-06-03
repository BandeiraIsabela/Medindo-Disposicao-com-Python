# Medindo-Disposicao-com-Python

## Sobre o Projeto

Este projeto implementa um Sistema Especialista baseado em Lógica Fuzzy para estimar o nível de disposição humana a partir de fatores relacionados ao bem-estar e à rotina diária.

A proposta surgiu como trabalho da disciplina de Inteligência Artificial II da Universidade Católica de Brasília (UCB), utilizando a biblioteca Scikit-Fuzzy em Python para modelar conhecimento humano por meio de regras linguísticas.

Diferentemente de modelos tradicionais, a lógica fuzzy permite representar conceitos subjetivos como "sono adequado", "alimentação boa" ou "estresse alto", tornando a análise mais próxima do raciocínio humano.

---

## Objetivo

Desenvolver um sistema inteligente capaz de estimar o nível de disposição de uma pessoa considerando múltiplos fatores do cotidiano, transformando informações qualitativas em um resultado quantitativo.

---

## Tecnologias Utilizadas

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-Fuzzy (skfuzzy)
- Jupyter Notebook

---

## Variáveis de Entrada

O sistema utiliza cinco variáveis antecedentes:

| Variável | Faixa |
|-----------|--------|
| Horas de Sono | 0 a 12 horas |
| Qualidade do Sono | 0 a 10 |
| Intensidade de Esforço Físico | 0 a 100 |
| Qualidade da Alimentação | 0 a 10 |
| Nível de Estresse | 0 a 10 |

### Classificações Linguísticas

#### Horas de Sono
- Curto
- Adequado
- Prolongado

#### Qualidade do Sono
- Ruim
- Regular
- Boa

#### Esforço Físico
- Leve
- Moderado
- Intenso

#### Alimentação
- Ruim
- Regular
- Boa

#### Estresse
- Baixo
- Médio
- Alto

---

## Variável de Saída

### Nível de Disposição

Faixa: **0 a 100%**

Classificações:

- Baixa
- Média
- Alta

---

## Funções de Pertinência

O projeto utiliza dois tipos principais de funções fuzzy:

### Trapezoidais (`trapmf`)
Aplicadas aos estados extremos, onde existe uma região de pertinência total.

Exemplos:
- Sono Curto
- Sono Prolongado
- Alimentação Boa
- Estresse Alto

### Triangulares (`trimf`)
Aplicadas aos estados intermediários para representar transições graduais.

Exemplos:
- Sono Adequado
- Alimentação Regular
- Disposição Média

---

## Base de Regras

O sistema foi construído com aproximadamente 20 regras fuzzy do tipo:

SE condição ENTÃO resultado

Exemplos:

SE Sono é Adequado
E Alimentação é Boa
ENTÃO Disposição é Alta
SE Estresse é Alto
ENTÃO Disposição é Baixa
SE Sono é Curto
E Estresse é Alto
ENTÃO Disposição é Baixa

As regras foram elaboradas para reproduzir comportamentos observados no cotidiano e simular a tomada de decisão humana.

Evolução do Projeto
Versão 1 (V1)

Modelo inicial composto por:

Horas de Sono
Qualidade do Sono
Esforço Físico

## Objetivo:

Validar a arquitetura fuzzy.
Testar o mecanismo de inferência.
Versão 2 (V2)

Versão final do projeto.

Novas variáveis adicionadas:

Qualidade da Alimentação
Nível de Estresse

## Melhorias:

Maior precisão dos resultados.
Regras mais realistas.
Redução de saltos bruscos na inferência.
Melhor representação da disposição humana.
Processo de Inferência

O sistema segue as etapas clássicas da lógica fuzzy:

Fuzzificação das entradas.
Aplicação das regras fuzzy.
Agregação dos resultados.
Defuzzificação pelo método do Centroide.

O resultado final é um valor numérico entre 0 e 100 que representa o nível de disposição estimado.

## Resultados

Foram realizados aproximadamente 40 cenários de teste para validar o comportamento do sistema.

Observações:

Cenários com sono adequado, alimentação boa e baixo estresse resultaram em alta disposição.
Cenários com estresse elevado reduziram significativamente a disposição, mesmo quando outras variáveis apresentavam valores favoráveis.
O modelo apresentou comportamento consistente e interpretável.
Estrutura do Projeto
.
├── Projeto_Fuzzy_Disposição.ipynb
├── Relatório Final.pdf
├── README.md

## Como Executar
1. Clone o repositório
git clone https://github.com/seu-usuario/projeto-fuzzy-disposicao.git
2. Instale as dependências
pip install numpy pandas matplotlib scikit-fuzzy
3. Execute o Notebook
jupyter notebook

Abra:

Projeto_Fuzzy_Disposição.ipynb
Aplicações Futuras

Este projeto pode servir como base para:

Sistemas de recomendação de hábitos saudáveis;
Aplicativos de bem-estar;
Monitoramento de produtividade;
Assistentes pessoais inteligentes;
Sistemas híbridos Neuro-Fuzzy.
Equipe

## Grupo 07 – Inteligência Artificial II

Bianca Melliny de Lima Vaz
Guilherme Fernandes Rezende
Isabela Martins Bandeira
João Filipe Alves de Albuquerque Silva
Natália Ematné Kruchak

Professor: William Roberto Malvezzi

Universidade Católica de Brasília – UCB
