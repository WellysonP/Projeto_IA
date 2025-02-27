# Rede Neural para Predição de Defeitos em Motor Redutor

Este projeto implementa uma rede neural artificial para prever defeitos em motores redutores através da análise de áudio. O sistema processa arquivos de áudio, extrai características relevantes usando a Transformada Rápida de Fourier (FFT) e utiliza uma rede neural para classificar possíveis defeitos.

## Pré-requisitos

Para executar este projeto, você precisará ter instalado:

- Python 3.x
- Jupyter Notebook

### Bibliotecas Python Necessárias

Instale as seguintes bibliotecas usando pip:

```bash
pip install numpy
pip install librosa
pip install pandas
pip install scikit-learn
pip install seaborn
pip install matplotlib
```

## Estrutura do Projeto

```
.
├── ProjetoFinal.ipynb    # Notebook principal com o código
├── audios/               # Diretório contendo os arquivos de áudio
│   ├── defeito1/        # Subdiretório para cada tipo de defeito
│   ├── defeito2/
│   └── ...
└── resultados.csv       # Arquivo gerado com os resultados da análise
```

## Como Executar

1. Clone o repositório:
   ```bash
   git clone https://github.com/WellysonP/Projeto_IA.git
   cd Projeto_IA
   ```

2. Crie e ative um ambiente virtual Python:
   ```bash
   # Criar o ambiente virtual
   python -m venv venv

   # Ativar o ambiente virtual
   # No Linux/Mac:
   source venv/bin/activate
   # No Windows:
   .\venv\Scripts\activate
   ```

3. Instale as dependências no ambiente virtual:
   ```bash
   pip install -r requirements.txt
   ```

4. Certifique-se de que todos os arquivos de áudio estão organizados corretamente na pasta `audios/`, com cada tipo de defeito em sua respectiva subpasta.

5. Inicie o Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

4. Abra o arquivo `ProjetoFinal.ipynb` no navegador.

5. Execute todas as células do notebook em ordem (Células > Executar Tudo) ou execute uma por uma pressionando Shift + Enter.

## Fluxo de Processamento

1. O sistema lê os arquivos de áudio da pasta `audios/`
2. Para cada áudio:
   - Aplica a Transformada Rápida de Fourier (FFT)
   - Extrai os 5 maiores picos da FFT
   - Calcula métricas estatísticas (desvio padrão, kurtosis, RMS)
3. Gera um arquivo CSV com todas as características extraídas
4. Treina uma rede neural MLP (Multi-Layer Perceptron) para classificação
5. Avalia o desempenho do modelo usando métricas de classificação

## Resultados

Os resultados podem ser visualizados de duas formas:

1. No arquivo `resultados.csv` que contém todas as características extraídas dos áudios
2. No próprio notebook, onde são apresentadas:
   - Matriz de confusão
   - Relatório de classificação
   - Visualizações gráficas dos resultados
