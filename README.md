# Fastans-fast-BPE
Fastans is a Byte Pair Encoding algorithm for text nueral networks. I tried to make it simple and workable. As well as to understand how BPE algorithms work in general

# The essence of BPE
Byte Pair Encoding is a learning algorithm designed to find the most 
frequent pairs of symbols/tokens and combine them into new tokens. It then 
uses its knowledge to translate text into tokens at the byte level and then into 
numbers (tokens). This algorithm stands between the text and the neural network's 
knowledge table. After its execution, tokens (numbers) are sent to the neural network's knowledge table, after which the tokens are converted into a format understandable by the AI ​​(vector). 

# Tokens
A token (at the text level) is a whole made up of several 
symbols. It is translated into numbers using the algorithm's knowledge. 
This is also a token, only at the numerical level.

# Fastans functionality

## Base
Fastans is a class with functions

## Training exampple
```python
from fastans import fastans

stop_token = "<|EOT|>
num_mergers = 200
bpe = fastans(stop_token)

# get your dataset
text = "YOUR_DATASET" # list or str

bpe.train(text, num_mergers=num_mergers)
bpe.save("bpe_vocabulary") # saving in .txt format
```

# Warning:
Before using the encode and decode functions, you
need to train the BPE/add tokens with add function, since the BPE
uses its own knowledge when training, not magic.

# functions

| function |  what does |
|---|---|
| `train(text, num_mergers)` | Trains BPE on a given num_mergers  |
| `add(token)` | Adds a token to the dictonary, useful for adding special tokens |
| `encode(text)` | Converting text into tokens(numbers) |
| `decode(tokens)` | Converts token (numbers) to tokens (text) |
| `save(path)` | adds .txt to yur path and saves BPE knowladge to this file path |
| `load(fastans_obj, path)` | adds .txt to yur path and loads knowladge from your file path to the passed fastans object |

