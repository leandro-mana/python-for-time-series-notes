# Chapter 12: Deep Learning for Time Series

Deep learning offers a fundamentally different approach to time series
forecasting.  Instead of specifying a parametric model (AR, ARIMA, ETS),
we let neural networks *learn* the mapping from past observations to
future values directly from data.  This flexibility comes at a cost --
more data, more compute, and less interpretability -- but it unlocks
capabilities that classical methods cannot match: learning complex
non-linear patterns, handling high-dimensional multivariate inputs,
and producing multi-step forecasts in a single forward pass.

This chapter builds from neural network fundamentals through recurrent
architectures (RNN, LSTM, GRU) and encoder-decoder models, ending with
a survey of modern architectures that represent the current state of
the art.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_neural_network_fundamentals.ipynb` | Dense layers, activation functions, loss functions, optimizers, Keras 3 API, MLP for time series with windowed lag features |
| 2 | `02_rnn_and_lstm.ipynb` | Why sequences need special architectures, RNN hidden state and vanishing gradients, LSTM gates and cell state, GRU, stacked/bidirectional LSTMs, early stopping, recursive multi-step forecasting |
| 3 | `03_sequence_to_sequence.ipynb` | Multi-step forecasting strategies (recursive, direct, seq2seq), encoder-decoder LSTM architecture, teacher forcing, practical 12-month-ahead forecasting |
| 4 | `04_modern_architectures.ipynb` | Temporal Convolutional Networks (TCN), N-BEATS, Temporal Fusion Transformer (TFT), foundation models (TimesFM, Chronos, Lag-Llama), when to use deep learning vs statistical methods |

## Key Concepts

- **Dense (fully connected) layers** compute $\mathbf{h} = \sigma(\mathbf{W}\mathbf{x} + \mathbf{b})$, the building block of all neural networks
- **Recurrent Neural Networks (RNNs)** maintain a hidden state that carries information across time steps, but suffer from vanishing gradients on long sequences
- **Long Short-Term Memory (LSTM)** networks solve the vanishing gradient problem with a cell state "memory highway" and three learned gates (forget, input, output)
- **Gated Recurrent Units (GRUs)** simplify LSTM to two gates (reset, update) with comparable performance and fewer parameters
- **Sequence-to-sequence (Seq2Seq)** models use an encoder to compress the input sequence and a decoder to generate the output sequence, enabling direct multi-step forecasting
- **Temporal Convolutional Networks (TCNs)** apply dilated causal convolutions to achieve long receptive fields while remaining fully parallelizable
- **Modern architectures** (N-BEATS, TFT, foundation models) push performance further but require careful evaluation against simpler baselines
- **Practical guideline**: statistical methods (ETS, ARIMA) remain hard to beat on short, univariate series; deep learning shines on large-scale, complex, multivariate problems

## References

- [Portilla TSA Section 07: Deep Learning for Time Series](https://www.udemy.com/user/joseportilla/) -- LSTM with TensorFlow/Keras
- [Keras 3 Documentation](https://keras.io/keras_3/) -- modern multi-backend API
- [Hochreiter & Schmidhuber (1997). Long Short-Term Memory](https://www.bioinf.jku.at/publications/older/2604.pdf) -- the original LSTM paper
- [Cho et al. (2014). Learning Phrase Representations using RNN Encoder-Decoder](https://arxiv.org/abs/1406.1078) -- GRU and encoder-decoder architecture
- [Oreshkin et al. (2019). N-BEATS: Neural basis expansion analysis for interpretable time series forecasting](https://arxiv.org/abs/1905.10437)
- [Lim et al. (2021). Temporal Fusion Transformers for interpretable multi-horizon time series forecasting](https://arxiv.org/abs/1912.09363)
- [Goodfellow, Bengio & Courville (2016). *Deep Learning*](https://www.deeplearningbook.org/) -- comprehensive reference
