# Análise de Comentários do YouTube

Este projeto realiza a coleta e análise de comentários de vídeos no YouTube, aplicando técnicas de Processamento de Linguagem Natural (NLP), Análise de Sentimentos, Modelagem de Tópicos e Visualização de Dados. O objetivo principal é entender o engajamento do público em campanhas de marketing de jogos e explorar o sentimento por trás dos comentários dos usuários.

## Bibliotecas Utilizadas

- **Coleta de Dados**: `googleapiclient.discovery` (API YouTube)
- **Manipulação de Dados**: `pandas`
- **Visualização**: `matplotlib`, `seaborn`
- **NLP**: `langdetect`, `nltk`, `spacy`
- **Modelagem de Tópicos**: `gensim`
- **Visualização Interativa**: `pyLDAvis`

## Funcionalidade

### 1. Coleta de Comentários do YouTube

A função `coletar_comentarios` usa a YouTube API para coletar até 500 comentários de um vídeo específico. Ela retorna um DataFrame com informações sobre o autor, o comentário, o número de likes e a data/hora de publicação.

### 2. Processamento e Análise

Após a coleta, são realizadas análises sobre os dados:

- Estatísticas básicas, como média de likes e intervalo de tempo dos comentários.
- Preparação dos dados para análise de sentimentos e modelagem de tópicos (LDA).

### 3. Visualização

A visualização dos dados é feita com gráficos básicos utilizando `matplotlib` e `seaborn`, além de visualizações interativas com `pyLDAvis` para modelagem de tópicos.

### 4. NLP e Análise de Sentimentos

A análise de sentimentos é realizada usando a ferramenta VADER Sentiment, para categorizar os comentários em "positivo", "negativo" ou "neutro", ajudando a entender a opinião dos usuários sobre o vídeo.

## Análise Preditiva de Comentários

### 1. Regressão para Prever Likes

O objetivo é prever a quantidade de likes com base no conteúdo textual dos comentários e características booleanas, utilizando os modelos:

- **Random Forest Regressor**
- **XGBoost Regressor**

O processo inclui o pré-processamento com `TfidfVectorizer` para extrair características textuais e `StandardScaler` para normalizar features booleanas. A avaliação dos modelos é feita com métricas como MAE (Erro Absoluto Médio) e RMSE (Raiz do Erro Quadrático Médio).

### 2. Comparação de Modelos de Regressão

Vários modelos de regressão, como Random Forest, Gradient Boosting, XGBoost, e Regressão Linear, são comparados utilizando validação cruzada. Os resultados são visualizados em gráficos de barras.

### 3. Classificação de Humor nos Comentários

A classificação dos comentários em relação à presença de humor/ironia é realizada com:

- **Random Forest Classifier**
- **Logistic Regression**

O processo inclui vetorização de texto com `TfidfVectorizer` e avaliação dos modelos através de relatórios de classificação e matrizes de confusão.

## Etapas do Processo

### 1. Carregamento e Limpeza dos Dados

- **Carregamento de Dados**: O arquivo `comentarios_youtube.csv` é carregado com as informações de data e hora dos comentários.
- **Limpeza de Texto**: A função `limpeza_estrategica` remove links, normaliza termos e limpa caracteres especiais.
- **Criação de Colunas de Análise**: Colunas como "menções à Ubisoft", "menções ao jogo" e "comentários com risada" são geradas.

### 2. Análise Estatística

- **Engajamento**: Métricas como a média e o máximo de "likes" são analisadas.
- **Distribuição Temporal**: A distribuição de comentários por hora é analisada em relação ao engajamento.

### 3. Análise de Sentimento

O modelo **VADER** é utilizado para analisar os sentimentos dos comentários, categorizando-os como positivos, negativos ou neutros, e avaliando o impacto dos sentimentos nos likes.

### 4. Detecção de Tópicos com LDA

A análise de tópicos é realizada utilizando **LDA (Latent Dirichlet Allocation)**, com visualização interativa dos tópicos dominantes.

### 5. Análise Adicional

- **Impacto das Menções da Marca**: A relação entre menções à Ubisoft e ao jogo com o engajamento é analisada.
- **Análise Temporal Detalhada**: A relação entre o engajamento e os horários/dias da semana é analisada através de heatmaps.

### 6. Análise de Humor

Identificação de comentários com risadas e sua correlação com o engajamento e sentimentos.

### 7. Relatórios e Visualizações

Relatórios automáticos em formato `.txt` e gráficos em `.png` são gerados para sumarizar as principais descobertas do projeto.

---

Esse projeto oferece uma visão detalhada sobre o engajamento e sentimentos dos usuários nos comentários de vídeos no YouTube, utilizando técnicas avançadas de NLP e aprendizado de máquina.
