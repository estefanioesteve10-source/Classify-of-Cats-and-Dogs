# Classificação de Imagens: Cats vs Dogs 

Este projeto utiliza **Transfer Learning** (Aprendizado por Transferência) para classificar imagens de cães e gatos. O objetivo principal foi demonstrar como utilizar um modelo pré-treinado em larga escala para obter alta performance em um dataset menor.

##  Visão Geral do Projeto
O fluxo de trabalho seguiu os padrões modernos de Machine Learning:
1. **Análise de Dados:** Exploração do dataset filtrado de cães e gatos.
2. **Pipeline de Dados:** Uso de `tf.keras.utils.image_dataset_from_directory` para carregamento eficiente.
3. **Data Augmentation:** Aplicação de rotações e inversões aleatórias para robustez do modelo.
4. **Arquitetura do Modelo:**
   - Base: **MobileNet V2** (pré-treinada no ImageNet).
   - Camada de Classificação: Adição de uma camada de Global Average Pooling e uma camada Dense de saída.
5. **Treinamento em Duas Etapas:**
   - **Extração de Características:** Treino apenas das camadas superiores com a base congelada.
   - **Ajuste Fino (Fine-tuning):** Descongelamento das camadas do topo da MobileNet para refinamento dos pesos.

##  Resultados
O modelo foi capaz de atingir uma precisão elevada no conjunto de validação, superando significativamente modelos treinados do zero (from scratch).



## 🛠️ Tecnologias Utilizadas
* [Python](https://www.python.org/)
* [TensorFlow 2.x](https://www.tensorflow.org/)
* [Keras](https://keras.io/)
* [Matplotlib](https://matplotlib.org/) (para visualização dos dados e curvas de aprendizado)

##  Estrutura de Diretórios
- `/train`: Imagens para treinamento (1000 gatos, 1000 cachorros).
- `/validation`: Imagens para validação (500 gatos, 500 cachorros).

##  Como executar
1. Clone o repositório.
2. Certifique-se de ter o TensorFlow instalado.
3. Execute o notebook `transfer_learning.ipynb`.

---
*Projeto concluído como parte do curso "Classify Images of Cats and Dogs using Transfer Learning" da Google Cloud via Coursera.*
