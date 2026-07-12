# 🚗 Traffic Accident Analysis | Análise de Acidentes em Rodovias Federais

[![Python 3.10.7](https://img.shields.io/badge/python-3.10.7-blue.svg)](https://www.python.org/downloads/release/python-3107/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=flat&logo=numpy&logoColor=white)](https://numpy.org/)

Este projeto realiza um pipeline completo de Ciência de Dados e Machine Learning sobre os acidentes de trânsito registrados nas rodovias federais brasileiras, utilizando a base de dados oficial da **Polícia Rodoviária Federal (PRF)**. 

O escopo evoluiu de uma análise inicial para uma modelagem preditiva utilizando o algoritmo **kNN (K-Neighbors Classifier)** para classificar a gravidade dos sinistros. O projeto mitiga desafios clássicos de dados reais, como alta cardinalidade de variáveis categóricas, distribuições fortemente assimétricas e severo desbalanceamento de classes.

---

## 📂 Estrutura do Repositório e Pipeline

O projeto está estruturado em uma sequência lógica de notebooks dentro da pasta `Notebooks/`, representando cada etapa do ciclo de vida dos dados:

```text
├── Data/
│   └── Acidentes_PorOcorrencia(25&26).csv   # Base de dados com 83.909 linhas e 30 colunas
├── Notebooks/
│   ├── 1. EDA.ipynb                          # Análise Exploratória e Inconsistências
│   ├── 2. Encoding.ipynb                     # Engenharia de Features e Codificações
│   ├── 3. Feature_Selection.ipynb            # Seleção de Atributos (MI & RF)
│   └── 4. Balanceamento_de_Dados.ipynb       # Resampling, Pré-processamento e Modelagem
├── README.md                                 # Documentação principal
└── contributing.md                           # Guia de contribuição da equipe
```

## 🔬 Detalhes das Etapas

#### 1. Análise Exploratória de Dados (EDA)
* **Inspeção Geral**: Mapeamento da base com 83.909 registros e 30 variáveis qualitativas e quantitativas.  
* **Estatística Descritiva & Visualizações**: Identificação do comportamento temporal (picos de acidentes nos finais de semana, faixas de horários críticos) e geográficos (maiores incidências por UF e BR).  
* **Sanidade dos Dados**: Detecção de dados faltantes ocultos ou disfarçados e tratamento de formatações inconsistentes.  

#### 2. Engenharia de Recursos & Encoding
* **Codificação Cíclica**: Transformação da variável `dia_semana` em componentes de Seno e Cosseno, preservando a continuidade temporal.  
* **Target Encoding**: Uso estratégico do `TargetEncoder` para lidar com variáveis categóricas de altíssima cardinalidade (ex: `uf`, `municipio`, `tipo_acidente`), otimizando o espaço vetorial sem causar a explosão dimensional.  

#### 3. Seleção de Características (Feature Selection)
* **Redução Dimensional**: Eliminação de colunas redundantes e correlacionadas.  
* **Métricas de Relevância**: Filtro baseado em **Mutual Information (Informação Mútua)** e **Random Forest Feature Importance** para elencar os preditores de maior impacto discriminatório sobre a variável alvo.  

#### 4. Balanceamento de Dados & Modelagem
* **Tratamento do Desbalanceamento**: Implementação de estratégias de amostragem para lidar com o desbalanceamento severo da variável alvo (`classificacao_acidente`), visando maximizar a sensibilidade do modelo.  
* **Transformação de Distribuições**: Uso do `QuantileTransformer` para suavizar e uniformizar caudas longas e assimetrias brutas das variáveis numéricas.  
* **Modelagem Preditiva**: Otimização do classificador `KNeighborsClassifier` com pesos ajustados por distância.

## 🛠️ Como Executar

### Pré-requisitos
* IDE recomendada: **VS Code** ou **Jupyter Lab**
* Entre no google drive e baixe o arquivo csv: 🔗 [**arquivos_tran202526.csv**](https://drive.google.com/drive/folders/1pmPnVxdiHsBYCsrTSXWqax1NPrWmtIXD?usp=sharing)
   ```
   Todo o código foi produzido e rodou localmente no python 3.10.7
   ```

1. Clone o repositório:
   ```bash
     git clone https://github.com/arthlz/Traffic-Accident-Analysis.git
   ```
   
2. Acesse a pasta do projeto
   ```pasta
   cd Traffic-Accident-Analysis
   ```

3. No terminal, crie um ambiente virtual e ative-o
   ```bash
    python -m venv venv <- Cria o ambiente virtual
   
    - Dispositivos Windows:
    .\venv\Scripts\activate -< Ativa o ambiente virtual
   
    - Dispositivos Linux/Mac:
    source venv/bin/activate <- Ativa o ambiente virtual
   ```

4. Instale os requerimentos necessários:
   ```bash
   pip install -r requirements.txt
   ```

5. Abra e execute o notebook.
