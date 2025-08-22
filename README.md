Descrição detalhada do projeto

Nome do Projeto:
Sistema Local de Recomendação de Produtos com NLP e Grafo (Batch-ready)

Resumo do Projeto:
Este projeto implementa um sistema de recomendação de produtos totalmente offline, combinando NLP (DistilBERT), graph analysis (NetworkX) e machine learning (MLP). O sistema recebe reviews de usuários, transforma-as em embeddings semânticos, constrói um grafo de produtos baseado na similaridade das reviews e utiliza um MLP para prever notas médias, permitindo recomendar produtos relevantes para novas reviews.

O projeto foi desenvolvido para demonstrar habilidades em machine learning, NLP, graph analysis, batch processing e engenharia de dados.

Tecnologias utilizadas
Python – Linguagem principal do projeto.
PyTorch – Framework para deep learning, usado para:
Extrair embeddings de texto com DistilBERT.
Treinar o modelo MLP para prever ratings.
Calcular similaridade entre embeddings com cosine_similarity.
Transformers (Hugging Face) – Biblioteca para NLP, usada para:
Tokenizar reviews (AutoTokenizer).
Obter embeddings contextualizados de reviews (AutoModel).
NetworkX – Biblioteca para graph analysis, usada para:
Criar grafo de produtos, conectando produtos com reviews semanticamente similares.
Visualizar relações entre produtos.
scikit-learn (LabelEncoder) – Para codificar IDs de produtos em índices numéricos.
Matplotlib – Para visualização do grafo.
NumPy & pandas – Para manipulação de dados e construção do dataset fictício.
Batch processing – Tanto no cálculo de embeddings quanto no treinamento do MLP, para eficiência e escalabilidade.
DataLoader (PyTorch) – Para treinamento do MLP em batches.

Pipeline do código
Criação do dataset local
10 produtos fictícios, 5 reviews cada, com notas simuladas (2 ou 5).
Código totalmente offline, sem downloads externos de datasets.
NLP: embeddings com DistilBERT
Cada review é convertida em embedding de 768 dimensões.
Processamento em batches para reduzir uso de memória e acelerar execução.
Grafo de produtos
Cada produto é um nó no grafo.
Produtos com reviews semanticamente similares (cosine similarity acima de threshold) recebem uma aresta.
Visualização do grafo usando NetworkX + Matplotlib.
Features médias por produto
Para cada produto, calcula embedding médio das suas reviews.
Calcula nota média do produto com base nas reviews.
MLP para previsão de nota
Modelo de feedforward (MLP) que mapeia embeddings médios para nota média do produto.
Treinado em batches usando DataLoader do PyTorch.
Otimização com Adam e loss MSE.

Função de recomendação:
Recebe uma nova review do usuário.
Calcula embedding da review.
Compara com embeddings médios dos produtos usando cosine similarity.
Retorna os top 3 produtos mais similares.
Teste de recomendação
O código inclui uma review exemplo e retorna produtos recomendados com base na similaridade semântica.

Diferenciais
100% offline, sem necessidade de acesso a datasets externos.
Batch processing, garantindo performance mesmo com datasets maiores.
Pipeline completo de NLP → grafo → features médias → MLP → recomendação.
Visualização do grafo, mostrando relações entre produtos.

Ideal para demonstração prática de skills em IA/ML, pronto para adaptação em datasets reais ou ambientes em nuvem (AWS SageMaker, Bedrock, etc.).
