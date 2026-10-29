# Otimização da Classificação Supervisionada de Textos sobre a Atividade Anticancerígena de Polifenóis

Repositório com o código-fonte, dados e documentação do Trabalho de Conclusão de Curso (TCC) em Ciência da Computação desenvolvido no **Instituto Federal de Educação, Ciência e Tecnologia do Sul de Minas Gerais – Câmpus Muzambinho**.

* **Autor:** Matheus Correia Pedroza  
* **Orientador:** Prof. Dr. Ramon Gustavo Teodoro Marques da Silva  
* **Ano:** 2022  

---

## 📌 Visão Geral

Com o rápido crescimento da literatura científica na área biomédica (indexada em bases como o PubMed/MEDLINE), a extração de conhecimento manual tornou-se uma tarefa inviável. Este projeto investiga o impacto de diferentes técnicas de:
1. **Pré-processamento de Linguagem Natural (PLN)**;
2. **Representação Textual (Espaço Vetorial e Embeddings)**;
3. **Algoritmos de Classificação (Aprendizado de Máquina e Aprendizado Profundo)**.

O objetivo principal é classificar resumos científicos em relação à comprovação da atividade anticancerígena de compostos polifenólicos, otimizando as métricas de desempenho em comparação com trabalhos da literatura (Silva, 2019).

---

## 📂 Estrutura do Repositório

```text
├── datasets/
│   ├── Corpus_não_processado.csv      # 400 resumos originais extraídos do PubMed
│   ├── Corpus_processado.csv          # Resumos após pipeline de limpeza e lematização
│   ├── Corpus_processado_test.csv     # Partição separada para testes
│   └── stopwords.txt                  # Lista de palavras de paragem utilizadas
│
├── notebooks/
│   ├── Text_Pre_Processing.ipynb      # Tokenização, remoção de ruídos e normalização
│   ├── Text_Classification_Naive_Bayes.ipynb
│   ├── Text_Classification_TF_IDF+_Naive_Bayes.ipynb
│   ├── Text_Classification_Neural_Network.ipynb      # Redes Neurais Artificiais (MLP)
│   ├── Text_Classification_CNN_+_Word_Embedding.ipynb # Convolucional 1D com Embeddings
│   ├── Text_Classification_LSTM.ipynb                # Redes Recorrentes LSTM
│   ├── Confusion_Matrix.ipynb         # Geração de matrizes de confusão detalhadas
│   └── Curve_ROC.ipynb                # Curvas ROC e cálculo de AUC
│
├── docs/
│   ├── TCC Matheus Pedroza.pdf        # Monografia completa
│   └── Apresentação TCC.pptx          # Diapositivos da defesa
│
├── .gitignore
├── requirements.txt
└── README.md

⚙️ Metodologia e Experimentos
O estudo avaliou 21 configurações experimentais distintas (15 de Aprendizado de Máquina clássico e 6 de Aprendizado Profundo):

1. Pré-processamento
Remoção de stopwords, pontuação, dígitos e caracteres especiais.

Radicalização (Stemming) com NLTK e Lematização.

Filtragem por frequência de termos no vocabulário.

2. Formas de Representação
TF (Term Frequency), IDF e TF-IDF.

CountVectorizer (frequência absoluta booleana/contagem).

Word Embeddings densos e vetores pré-treinados com Word2Vec.

3. Modelos de Classificação
Classificadores Probabilísticos: Naive Bayes (Multinomial e Gaussiano).

Redes Neurais Artificiais (MLP): Construídas via Keras/TensorFlow.

Aprendizado Profundo (Deep Learning):

Convolutional Neural Networks (CNN 1D) para extração local de padrões n-gramas.

Long Short-Term Memory (LSTM) para captura de dependências contextuais e ordenação sequencial.

📊 Principais Resultados
Os modelos baseados em Aprendizado Profundo superaram os classificadores convencionais:

Experimento,Representação,Algoritmo,Acurácia,AUC (ROC)
Exp. 1 (DL),Word2Vec,Deep Learning (CNN),"99,0%","0,98"
Exp. 6 (DL),Vetores de Similaridade,Deep Learning (LSTM),"99,0%","0,98"
Exp. 2 (DL),Word Embedding,Deep Learning (CNN),"98,0%","0,99"
Exp. 8 (ML),CountVectorizer,Redes Neurais (MLP),"98,0%","0,97"
Exp. 2 (ML),Term Frequency (TF),Redes Neurais (MLP),"97,0%","0,97"
Exp. 15 (ML),Probabilidade de Termos,Naive Bayes,"93,0%","0,95"

🚀 Como Executar Localmente
Pré-requisitos
Python 3.8 ou superior

Gerenciador de pacotes pip

Instalação
Clone o repositório:

Bash
git clone [https://github.com/SEU_USUARIO/SEU_REPOSITORIO.git](https://github.com/SEU_USUARIO/SEU_REPOSITORIO.git)
cd SEU_REPOSITORIO
Crie e ative um ambiente virtual:

Bash
python -m venv venv
# No Windows:
venv\Scripts\activate
# No Linux/macOS:
source venv/bin/activate
Instale as dependências necessárias:

Bash
pip install -r requirements.txt
(Exemplo de conteúdo para o requirements.txt: numpy, pandas, scikit-learn, nltk, tensorflow, matplotlib, seaborn, jupyter).

Descarregue os recursos do NLTK no console Python:

Python
import nltk
nltk.download('stopwords')
nltk.download('punkt')
Inicie o Jupyter Notebook para reproduzir as simulações:

Bash
jupyter notebook
📜 Referência Acadêmica
Caso este trabalho ou base de dados seja útil para a sua pesquisa, utilize a seguinte citação:

Snippet de código
@monography{pedroza2022otimizacao,
  title={Otimização da Classificação Supervisionada de Textos sobre a Atividade Anticancerígena de Polifenóis},
  author={Pedroza, Matheus Correia},
  year={2022},
  pages={47},
  type={Trabalho de Conclusão de Curso (Graduação em Ciência da Computação)},
  school={Instituto Federal de Educação, Ciência e Tecnologia do Sul de Minas Gerais, Câmpus Muzambinho},
  address={Muzambinho, MG}
}
