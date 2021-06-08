# AegisML based on Fine-tuning a Bert Model
A copy of our collab notebook from [here](https://colab.research.google.com/drive/1xCu9iNFKGcy2_QBfYbu6bzArLx6Q-Po1?usp=sharing#scrollTo=Kb1noggS_qY0).

BERT is basically an Encoder stack of transformer architecture. BERT’s key technical innovation is applying the bidirectional training of Transformer, BERT uses self-attention on the encoder side and attention on the decoder side. 

BERT makes use of Transformer, an attention mechanism that learns contextual relations between words (or sub-words) in a text. In its vanilla form, Transformer includes two separate mechanisms — an encoder that reads the text input and a decoder that produces a prediction for the task. Since BERT’s goal is to generate a language model, only the encoder mechanism is necessary.

### **Data Cleaning**
We use panda dataframe to modify the table of data and regex to clean them up

### **Pre Processing**
The data we use based on maximal 256 of token but bert can have max 512 lengths of the token.
There are 2 type of data we need to make before train them
- **Input Ids**: this process when we tokenize the sequence of sentences to token
- **Attention Mask**: this process when we masking the sequence of sentences    

After we build the data on array we need to map them on tensor format we use tf.data.Dataset.from_tensor_slices to help to transform the data

### **Labeling**
We have 3 type of labels as the output of prediction
- Normal
- Abusive
- Hate Speech

### **Credit**
IndoBERT was trained and evaluated by Bryan Wilie*, Karissa Vincentio*, Genta Indra Winata*, Samuel Cahyawijaya*, Xiaohong Li, Zhi Yuan Lim, Sidik Soleman, Rahmad Mahendra, Pascale Fung, Syafri Bahar, Ayu Purwarianti [More info](https://huggingface.co/indobenchmark/indobert-base-p1).

Muhammad Okky Ibrohim and Indra Budi. 2019. Multi-label Hate Speech and Abusive Language Detection in Indonesian Twitter [More info](https://www.kaggle.com/ilhamfp31/indonesian-abusive-and-hate-speech-twitter-text).


