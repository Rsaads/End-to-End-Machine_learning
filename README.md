# End-to-End-Machine_learning

# Predição de Ataques Cardíacos no Japão com Machine Learning

## Descrição do Projeto
Este projeto tem como objetivo desenvolver um modelo de machine learning para prever a ocorrência de ataques cardíacos na população japonesa, com base em dados de saúde. O conjunto de dados utilizado foi extraído do Kaggle ([link](https://www.kaggle.com/datasets/ashaychoudhary/heart-attack-in-japan-youth-vs-adult)). O projeto explora diferentes técnicas de processamento de dados, normalização, aprendizado de máquina e deep learning para realizar a classificação binária de risco de ataque cardíaco.

## Tecnologias Utilizadas
- **Linguagem**: Python 3.9
- **Bibliotecas**:
  - TensorFlow/Keras (para construção e treinamento do modelo de deep learning)
  - Scikit-learn (para normalização e modelos de aprendizado de máquina tradicionais)
  - Pandas e NumPy (para manipulação de dados)
  - Matplotlib (para visualização dos dados)
  - MLflow (para rastreamento de experiências e logging de hiperparâmetros)

## Estrutura do Projeto
- `japan_heart_attack_dataset.csv`: Arquivo com os dados utilizados no treinamento do modelo.
- `seu_script.py`: Script principal contendo todo o pipeline de treinamento e avaliação do modelo.
- `Dockerfile`: Arquivo para conteinerização do projeto.
- `requirements.txt`: Lista das dependências necessárias para executar o projeto.

## Etapas do Projeto
1. **Carregamento e Limpeza dos Dados**
   - Remoção de valores duplicados.
   - Exclusão de colunas irrelevantes.
   - Análise exploratória dos dados (distribuição de variáveis, correlações, etc.).
   
2. **Pré-processamento**
   - Conversão de variáveis categóricas em variáveis dummy.
   - Normalização das features numéricas com `MinMaxScaler`.
   - Divisão dos dados em conjuntos de treino e teste (80/20).
   
3. **Treinamento de Modelos**
   - **SVM (Support Vector Machine)** com kernel linear.
   - **Rede Neural** utilizando TensorFlow/Keras com:
     - 2 camadas densas ocultas (64 e 32 neurônios, respectivamente) com função de ativação `ReLU`.
     - Camada de saída com 1 neurônio e ativação `sigmoid`.
     - Otimizador `Adam` com taxa de aprendizado de 0.001.
     - Função de perda `binary_crossentropy`.
   
4. **Avaliação do Modelo**
   - Cálculo de acurácia, matriz de confusão e relatório de classificação.
   - Registro de hiperparâmetros e métricas no MLflow.

5. **Testes Unitários**
   - Implementação de testes com `unittest` para verificar se o modelo produz apenas valores esperados (0 ou 1).

## Execução do Projeto
### Ambiente Local
1. Clone o repositório:
   ```bash
   git clone <seu-repositorio>
   cd <seu-repositorio>
   ```
2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```
3. Execute o script:
   ```bash
   python seu_script.py
   ```

### Uso com Docker
1. Construa a imagem Docker:
   ```bash
   docker build -t meu_modelo_ml .
   ```
2. Rode o container:
   ```bash
   docker run -it meu_modelo_ml
   ```

---
Este projeto foi desenvolvido para fins educacionais e experimentação em aprendizado de máquina e deep learning.

