# VGGish

A `torch`-compatible port of [VGGish](https://github.com/tensorflow/models/tree/master/research/audioset), a feature embedding frontend for audio classification models. The weights are ported directly from the tensorflow model, so embeddings created using `torchvggish` will be identical.

I forked this repo from [https://github.com/harritaylor/torchvggish.git](https://github.com/harritaylor/torchvggish.git) and made some changes. Many thanks!

## Usage

```python
import torch

model = torch.hub.load('harritaylor/torchvggish', 'vggish')
model.eval()

# Download an example audio file
import urllib
url, filename = ("http://soundbible.com/grab.php?id=1698&type=wav", "bus_chatter.wav")
try: urllib.URLopener().retrieve(url, filename)
except: urllib.request.urlretrieve(url, filename)

model.forward(filename)
```

[1]  S. Hershey et al., ‘CNN Architectures for Large-Scale Audio Classification’,\
    in International Conference on Acoustics, Speech and Signal Processing (ICASSP),2017\
    Available: [https://arxiv.org/abs/1609.09430](https://arxiv.org/abs/1609.09430), [https://ai.google/research/pubs/pub45611](https://ai.google/research/pubs/pub45611).
