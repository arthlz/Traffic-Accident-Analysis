### Traffic Accident Analysis | Análise de Acidentes em Rodovias Federais

Este projeto tem como objetivo realizar uma análise exploratória de dados (EDA) sobre os acidentes de trânsito registrados nas rodovias federais brasileiras. Utilizando a base de dados da Polícia Rodoviária Federal (PRF), buscamos identificar padrões, causas principais e perfis de gravidade para auxiliar na compreensão da segurança viária no país.
----

### 📌 Sobre os Dados
Os dados analisados (baseados no arquivo arquivos_tran202526.csv) compreendem registros detalhados de ocorrências, incluindo:

- Localização: UF, BR, KM e Município.

- Temporalidade: Data, horário, dia da semana e fase do dia.

- Circunstâncias: Causa presumida, tipo de acidente, condição meteorológica e traçado da via.

- Gravidade: Quantidade de pessoas envolvidas, feridos leves/graves, ilesos e óbitos.

- Veículos: Quantidade de veículos envolvidos em cada sinistro.

-----

### 🚀 Tecnologias Utilizadas
Linguagem: Python 3.10.7

Bibliotecas de Manipulação: Pandas, NumPy

Visualização de Dados: Matplotlib, Seaborn

Ambiente: Jupyter Notebook (.ipynb)

-------

# 📊 Principais Objetivos da Análise
**Identificação de Causas**: Mapear os fatores mais comuns que levam a acidentes (ex: reação tardia, velocidade incompatível).

**Análise Geográfica**: Verificar quais estados (uf) e rodovias (br) apresentam maior índice de ocorrências.

**Perfil de Gravidade**: Correlacionar o tipo de pista e condições climáticas com o número de vítimas fatais e feridos graves.

**Sazonalidade**: Entender o comportamento dos acidentes por dia da semana e horários críticos.

--------

# 📂 Estrutura do Repositório
CD_Equipe4.ipynb: Notebook principal contendo todo o pipeline de limpeza, análise e visualização.

arquivos_tran202526.csv: Conjunto de dados utilizado no projeto.

README.md: Documentação do projeto.

🛠️ Como Executar:

# Reprodutibilidade(Recomendo o uso do vscode como IDE):
   ```
   Todo o código foi produzido e rodou localmente no python 3.10.7
   ```

Passo 1: Clone o repositório:
   ```bash
     git clone https://github.com/arthlz/Traffic-Accident-Analysis.git
   ```
   
2. Acesse a pasta do projeto
   ```pasta
   cd Traffic-Accident-Analysis
   ```

3. No terminal, crie um ambiente virtual e ative-o
   ```Venv
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
