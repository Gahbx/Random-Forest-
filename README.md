# Random-Forest-# 🌲 Previsão de Acionamento de Seguro usando Random Forest

Este projeto foi desenvolvido com o objetivo principal de **estudar e aplicar o algoritmo de Random Forest (Floresta Aleatória)**. O caso de uso prático escolhido foi prever qual tipo de serviço de seguro um cliente tem maior probabilidade de acionar com base em suas características (Idade, Preço do Seguro e CEP).

---

## 🧠 Embasamento Conceitual: O que é Random Forest?

O **Random Forest** (Floresta Aleatória) é um algoritmo de aprendizado de máquina supervisionado que baseia seu funcionamento na criação de um grande número de **Árvores de Decisão (Decision Trees)** durante a fase de treinamento. Ele é amplamente utilizado tanto para problemas de *Classificação* quanto de *Regressão*.

**Como funciona?**
Em vez de depender de uma única árvore de decisão (que é propensa a sofrer de *overfitting* ou superajuste, memorizando os dados de treino), o Random Forest cria uma "floresta" de várias árvores. 
1. **Bootstrap / Bagging:** Cada árvore é treinada com um subconjunto aleatório dos dados.
2. **Aleatoriedade de Features:** Em cada divisão da árvore, apenas um subconjunto aleatório das variáveis é considerado.
3. **Votação Majoritária:** Na hora de prever um novo dado (no caso de classificação), cada árvore dá o seu "voto". A previsão final do Random Forest é a classe que recebeu mais votos em toda a floresta.

## 💻 Sobre o Projeto Prático

O projeto analisa uma base de dados de clientes de uma seguradora e constrói um modelo capaz de prever a categoria do serviço utilizado.

### 📊 O Conjunto de Dados
Os dados estão divididos em duas abas num arquivo Excel (`BaseDados_FlorestaDeDecisão.xlsx`):
* **Plan1 (Dados de Treino/Teste):** Contém 500 registros históricos.
* **Plan2 (Novas Vendas):** Contém novos clientes para os quais queremos prever o comportamento.

**Atributos (Features):**
* `Idade`: Idade do cliente.
* `Preço Seguro`: Valor pago na apólice.
* `CEP`: Localização do cliente.

**Variável Alvo (Target):**
* `Serviço`: Tipo de evento registrado pelo cliente:
  * `1` - Não usou
  * `2` - Usou serviço comum
  * `3` - Furto

### 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python
* **Manipulação de Dados:** `pandas`, `numpy`
* **Visualização:** `seaborn`, `matplotlib`
* **Machine Learning:** `scikit-learn` (`RandomForestClassifier`, `train_test_split`, `confusion_matrix`, `classification_report`)

### 🚀 Etapas de Execução

1. **Análise Exploratória de Dados (EDA):** Verificação de tipos de dados, contagens e geração de gráficos (Histogramas e Boxplots) para entender o comportamento das idades, preços e CEPs em relação aos tipos de serviços acionados.
2. **Separação de Dados:** Divisão da base em 70% para treinamento (350 registros) e 30% para testes (150 registros).
3. **Modelagem:** Treinamento do modelo `RandomForestClassifier` configurado para construir 500 árvores (`n_estimators=500`).
4. **Avaliação do Modelo:** 
   * **Acurácia (Accuracy):** O modelo obteve **86%** de taxa de acerto nos dados de teste.
   * **Matriz de Confusão e Report:** Foi gerado um relatório de classificação mostrando excelentes valores de precisão e recall (ex: 94% de precisão para a categoria "1 - Não usou").
5. **Previsões Finais:** Aplicação do modelo treinado na planilha de novos clientes (`Plan2`) e adição da coluna `Previsao do Modelo` para auxiliar a tomada de decisão da empresa.

---

## 🤝 Como executar este projeto
1. Certifique-se de ter o Python instalado junto com as bibliotecas: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn` e `openpyxl` (para ler o excel).
2. Deixe o arquivo `BaseDados_FlorestaDeDecisão.xlsx` no mesmo diretório do seu script/notebook.
3. Execute as células do Jupyter Notebook sequencialmente.

---
*Projeto criado para fins educacionais e aprimoramento de habilidades em Ciência de Dados e Machine Learning.*
