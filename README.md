# **Projeto de Limpeza e Pré-processamento de Dados de E-commerce Olist**

## Descrição do Projeto
Este projeto tem como objetivo principal a limpeza e o pré-processamento de dois datasets relacionados a um e-commerce fictício, Olist: `olist_products_dataset.csv` e `olist_orders_dataset.csv`. O processo envolve a ingestão dos dados, padronização de strings, tratamento de valores nulos e aplicação de regras de negócio específicas, culminando na formatação de datas e na geração de um relatório de status.

## Guia de Execução
1.  **Preparação do Ambiente:** Certifique-se de ter um ambiente Python configurado (preferencialmente Google Colab ou Jupyter Notebook). As bibliotecas necessárias são `csv`, `os`, `re`, `datetime` e `numpy`, que são geralmente parte da instalação padrão ou podem ser instaladas via `pip`.
2.  **Upload dos Datasets:** Faça o upload dos arquivos `olist_products_dataset.csv` e `olist_orders_dataset.csv` para o diretório de trabalho do seu ambiente (em Colab, para a sessão de armazenamento).
3.  **Execução do Script:** Execute as células do notebook sequencialmente. O script realizará as seguintes etapas:
    *   **Ingestão de Dados:** Carregará os dados dos arquivos CSV para listas de dicionários Python.
    *   **Transformação de Strings:** Padronizará os nomes das categorias de produtos (minúsculas, sem espaços extras, sem caracteres especiais).
    *   **Limpeza de Nulos nos Produtos:** Tratará valores nulos em categorias e dimensões físicas (preenchimento com 'sem categoria' ou média).
    *   **Regras de Negócio e Formatação de Datas:** Validará a regra de negócio para pedidos cancelados e formatará datas para 'DD/MM/YYYY'.
    *   **Relatório de Status:** Exibirá um sumário estatístico das operações de limpeza.

## Reflexão Teórica: Como a Limpeza de Dados Evita Overfitting ou Viés em Modelos de IA
A limpeza de dados é uma etapa crucial no pipeline de machine learning e inteligência artificial, impactando diretamente a qualidade e a confiabilidade dos modelos preditivos. Ela evita overfitting e viés de várias maneiras:

*   **Redução de Ruído:** Dados ruidosos ou incorretos (erros de digitação, medições falhas) podem levar um modelo a aprender padrões que não existem na realidade, resultando em overfitting. Ao limpar esses dados, o modelo foca nos padrões verdadeiros, melhorando sua capacidade de generalização.
*   **Tratamento de Valores Nulos:** Valores ausentes podem ser interpretados de forma inadequada pelo modelo. A imputação de nulos (como com a média, moda ou mediana) ou a remoção cuidadosa de registros com muitos nulos garante que o modelo não crie viés baseado na ausência de informação ou na forma como esses nulos são tratados por padrão pelas bibliotecas.
*   **Padronização e Consistência:** A padronização de strings e formatos (como categorias e datas neste projeto) evita que o modelo trate a mesma entidade como diferentes. Por exemplo, 'Perfumes' e 'perfumes' seriam vistos como duas categorias distintas sem a limpeza, levando a um subaproveitamento de dados e potenciais vieses nas previsões relacionadas a essa categoria.
*   **Validação de Regras de Negócio:** Erros lógicos nos dados (como datas de entrega nulas para pedidos não cancelados) introduzem inconsistências que podem confundir o modelo. A correção ou identificação dessas violações garante que o modelo não aprenda a partir de informações contraditórias, o que poderia gerar previsões errôneas ou enviesadas.
*   **Remoção de Duplicatas e Outliers:** Duplicatas podem super-representar certas observações, levando o modelo a dar peso indevido a elas. Outliers, se não tratados, podem distorcer as distribuições e parâmetros do modelo, resultando em previsões imprecisas ou modelos excessivamente complexos para acomodar esses pontos anômalos.

Em resumo, dados limpos e bem estruturados permitem que os modelos de IA aprendam a partir de informações precisas e representativas, resultando em maior acurácia, melhor capacidade de generalização (evitando overfitting) e menor probabilidade de introduzir vieses decorrentes da má qualidade dos dados.
