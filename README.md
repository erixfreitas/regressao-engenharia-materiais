🧱 Análise de Resistência à Compressão do Concreto
Projeto de Ciência de Dados aplicado à previsão da resistência à compressão do concreto com modelos de regressão. Integra etapas de análise exploratória, engenharia de atributos, modelagem com Random Forest e Regressão Linear, e interpretação com SHAP.

📑 Índice
1. 📌 Objetivos do Projeto
2. 📊 Etapas do Processo
3. 🔍 Explicação dos Blocos de Código
4. 📂 Como Clonar e Executar o Projeto
5. 📦 Instalação de Bibliotecas
6. 📚 Glossário
7. 🧠 Referências

📌 Objetivos do Projeto
* Explorar correlações entre variáveis numéricas.
* Visualizar relações entre atributos e resistência à compressão.
* Avaliar a performance de modelos preditivos: Random Forest e Regressão Linear.
* Interpretar os resultados utilizando SHAP values (explicabilidade de modelos).

📊 Etapas do Processo
1. Carregamento de dados
2. Limpeza e pré-processamento
3. Análise exploratória e visualizações
4. Engenharia de variáveis
5. Modelagem com Random Forest e Linear Regression
6. Otimização com GridSearchCV
7. Interpretação com SHAP

🔍 Explicação dos Blocos de Código
1. Carregamento e Limpeza de Dados

```def carregar_dados(caminho_csv: str) -> pd.DataFrame:
    ...```
Carrega o CSV, remove valores nulos e retorna o DataFrame limpo.

2. Matriz de Correlação

```def plot_matriz_correlacao(df: pd.DataFrame) -> None:
    ...```
Gera um heatmap com a correlação entre variáveis numéricas.

3. Relação Variáveis x Resistência

```def plot_dispersao_variaveis(df: pd.DataFrame) -> None:
    ...```
Mostra a dispersão das variáveis Cement, Water e Age em relação à resistência.

4. Resistência Média por Categoria

```def plot_resistencia_media(df: pd.DataFrame) -> None:
    ...```
Exibe a média da resistência por categoria de força (Strength Category).

5. Engenharia de Variáveis

```def preparar_variaveis(df: pd.DataFrame) -> pd.DataFrame:
    ...```
Converte categorias em dummies (variáveis binárias) e renomeia colunas.

6. Modelagem

```def treinar_modelos(X_train, X_test, y_train, y_test):
    ...```
Treina Random Forest e Regressão Linear, exibindo R² e MAE.

7. Otimização com GridSearchCV

```params = {...}
grid_model = GridSearchCV(...)```
Ajusta hiperparâmetros para o Random Forest com validação cruzada.

8. Análise de Resíduos

```residuo = y_test - y_pred_grid...```
Verifica padrões nos erros do modelo. Idealmente, resíduos devem ser aleatórios.

9. Interpretação com SHAP

```def interpretar_modelo(modelo, X_test):
    ...```
Explica a influência de cada variável nas previsões usando SHAP values.

📂 Como Clonar e Executar o Projeto

🔁 Clonando o repositório

```git clone https://github.com/erixfreitas/regressao-engenharia-materiais
cd projeto-concreto```
Substitua seu-usuario pelo seu nome de usuário do GitHub.

📦 Instalação de Bibliotecas

📁 Opção 1: Usando requirements.txt

```pip install -r requirements.txt```

⚙️ Opção 2: Manual (pip)

```pip install pandas numpy matplotlib seaborn scikit-learn shap```

```📚 Glossário

| Termo                         | Descrição                                                          |
| ----------------------------- | ------------------------------------------------------------------ |
| **Resistência à Compressão**  | Medida da capacidade do concreto suportar cargas sem esmagar.      |
| **SHAP (SHapley values)**     | Técnica para explicar a saída de modelos preditivos complexos.     |
| **R² (R-squared)**            | Quanto da variação da variável dependente é explicada pelo modelo. |
| **MAE (Erro Absoluto Médio)** | Média das diferenças absolutas entre valores previstos e reais.    |
| **Random Forest**             | Algoritmo de ensemble baseado em múltiplas árvores de decisão.     |
| **Regressão Linear**          | Modelo estatístico simples para prever variáveis contínuas.        |
| **GridSearchCV**              | Técnica para encontrar a melhor combinação de hiperparâmetros.     |
| **Resíduos**                  | Diferença entre o valor real e o valor previsto.                   |