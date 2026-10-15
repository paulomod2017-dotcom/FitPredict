# 📈 FitPredict - Bot de Trading com Machine Learning e Meta-Modelo

O **FitPredict** é um algoritmo de trading para criptomoedas (focado em BTC-USDT) que opera em duas camadas de inteligência artificial. O objetivo é prever a direção (CALL/PUT) dos próximos candles de 5 minutos, sendo ideal para estudos em Opções Binárias e mercados de curto prazo.

⚠️ **Aviso Importante:** Este projeto ainda não atingiu a base necessária de 1.000 sinais para a ativação do Meta-Modelo e não foi testado em conta real. **Não utilize este código com dinheiro real.** O uso é estritamente educacional.

## 🧠 Arquitetura de Dupla Camada

O bot se diferencia por não confiar cegamente em um único modelo preditivo:

1. **Camada 1 (O Analista):** Um modelo `XGBoost` recebe dados de preço, tendências (EMA), volatilidade (ATR), força relativa (RSI/ADX) e limites (Bandas de Bollinger) para calcular a probabilidade do próximo candle. Sinais acima de 60% de confiança avançam.
2. **Camada 2 (O Chefe de Risco / Meta-Modelo):** Após 1.000 operações registradas, um segundo modelo entra em ação. Ele não olha para o mercado, mas para o *histórico de acertos e erros do próprio bot*. Se as condições atuais do mercado costumam gerar falsos positivos para o bot, o sinal é cancelado.

## 🛠️ Tecnologias Utilizadas

* **Python 3**
* **Pandas & NumPy:** Manipulação de dados e Feature Engineering.
* **Scikit-Learn & XGBoost:** Modelagem preditiva.
* **OKX API:** Coleta de dados de mercado em tempo real.

## 🚀 Como Executar

Como o projeto foi construído em formato de Notebook, a execução é muito direta:

1. Faça o download do arquivo `FitPredict.ipynb` (ou clone este repositório).
2. Abra o arquivo no **Google Colab** (recomendado) ou no seu Jupyter Notebook local.
3. Execute a primeira célula do código. Ela já fará a instalação de todas as bibliotecas necessárias automaticamente.
4. Execute o restante do notebook. 

*(Nota: Caso utilize o Google Colab, não esqueça de montar o seu Google Drive e verificar os caminhos no código para que o arquivo `historico_sinais_real1000.csv` seja salvo corretamente).*

## 🤝 Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir uma *Issue* ou enviar um *Pull Request* se tiver ideias para melhorar o Feature Engineering ou a lógica do Meta-Modelo.

---
*Desenvolvido com ☕ e Machine Learning por Paulo H(paulomod2017-dotcom).
