# Projeto da disciplina de algoritmos de inteligência artificial para classificação - 25E1_2  

## Índice  
- [Sobre](#Sobre)  
- [Pré-requisitos](#pré-requisitos)  
- [Objetivo](#objetivo)  
- [Metodologia](#metodologia)  

---

## Sobre  
Este projeto visa a **classificação da qualidade de vinhos verdes portugueses** utilizando algoritmos de **Machine Learning supervisionado**. O objetivo é construir um modelo que preveja se um vinho é **bom** ou **ruim**, baseado em suas propriedades físico-químicas.  

Para isso, foram utilizados **dados reais** de vinhos tintos e brancos, disponibilizados no [Kaggle](https://www.kaggle.com/datasets/rajyellow46/wine-quality).  

Os modelos analisados incluem:  
- **Regressão Logística**  
- **Árvores de Decisão**  
- **Máquina de Vetores de Suporte (SVM)**  

Os modelos foram comparados utilizando **validação cruzada k-fold (k=10)** e métricas como **acurácia, precisão, recall, F1-score e Curva ROC**.

---

## Pré-requisitos  
Para rodar o projeto, é necessário ter instalado:  

- [Conda](https://www.anaconda.com/download)  
- [Git](https://git-scm.com/downloads)  
- [VsCode](https://code.visualstudio.com/download)  
- Jupyter Notebook v7.0.8  
- Python v3.12.4  
- Anaconda v24.9.2 (Ambiente virtual chamado `"infnet-25E1_2"`)  

---

## Objetivo  
O principal objetivo deste projeto é construir e avaliar **modelos de classificação supervisionados** para prever a qualidade de vinhos brancos e tintos, baseando-se em atributos físico-químicos como **acidez, pH, açúcar residual, teor alcoólico, entre outros**.

Os resultados serão utilizados para indicar **qual modelo apresenta melhor desempenho** e verificar se ele pode ser aplicado a vinhos tintos com a mesma eficiência.

---

## Metodologia  
### **1. Processamento e Filtragem dos Dados**  
- **Base de dados**: Vinhos verdes portugueses (**tintos e brancos**).  
- **Criação da variável "opinion"**:
  - `0` (Ruim) → **Quality ≤ 5**  
  - `1` (Bom) → **Quality > 5**  
- **Divisão da base**: Separação dos vinhos brancos para treinamento e vinhos tintos para teste.  
- **Tratamento de valores ausentes**: Preenchimento com a média das colunas.  
- **Normalização dos dados**: Aplicação de `StandardScaler` para padronização das variáveis contínuas.  

### **2. Modelagem e Treinamento**  
- Treinamento de cinco modelos de classificação:  
  - **Regressão Logística**  
  - **Árvore de Decisão**  
  - **SVM (Support Vector Machine)**  
  - **Random Forest**  
  - **K-Nearest Neighbors (KNN)**  
- Aplicação de **validação cruzada estratificada (k=10)** para avaliação dos modelos.  
- Cálculo das métricas:
  - **Acurácia**
  - **Precisão**
  - **Recall**
  - **F1-score**  

### **3. Comparação dos Modelos (Curva ROC)**  
- Geração da **Curva ROC Média** para os modelos.  
- Escolha do melhor modelo com base na **AUC (Área sob a Curva ROC)**.  
- Justificativa da escolha do modelo ideal.  

### **4. Inferência com Vinhos Tintos**  
- Aplicação do **melhor modelo** nos vinhos tintos.  
- Comparação dos resultados com os vinhos brancos.  
- Avaliação de **possível viés** no modelo ao lidar com os vinhos tintos.  
