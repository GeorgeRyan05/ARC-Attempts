## Solution by Icecuber - Accuracy 18.00
This is based on https://www.kaggle.com/code/hansuelijud/template-arc2020-1st-place-solution-by-icecuber  
This was the winning solution of 2020, using Domain Specific Language (DSL) to approach it.

## Solution by fine-tuning Gemma - Accuracy 0.00
This is based on https://www.kaggle.com/code/hansuelijud/template-llama-3-8b-arc-prize-2024-inference and 
https://www.kaggle.com/code/hansuelijud/template-llama-3-8b-arc-prize-2024-finetuning.  
This requires additional dependencies to run offline for submission

I wanted to try using LLMs directly to solve this, but was unsuccessful with Gemma.  
Trying with Llama 3.1 may have helped, but I did not get access on kaggle quickly.  
In any case, smaller LLMs are known to perform poorly on this dataset.

## A potentially better approach
I believe the following approaches would help, though I have not implemented them yet:  
- Using vision models in addition to LLMs to identify "objects" better[^1][^2]. This can help LLMs deal with 2D data much better[^1][^3].
- Using multimodal models like phi-3.5-vision to understand the image better, though this may require further training, or an initial increase in resolution to work well[^1]
- Combining LLMs with DSL by having LLMs call or write common transformations and ideas[^4][^5]. This may be challenging since LLMs struggle with identifying locations, but could be helped by a vision model to locate "objects"
- Using an LLM to retry solutions a few times or until it identifies the solution as correct[^4]
- Using 2 methods (perhaps multimodal LLMs and LLMs with DSL)  until their solutions match to deal with slight errors. 

[^1]: [LLMs and the Abstraction and Reasoning Corpus: Successes, Failures, and the Importance of Object-based Representations](https://arxiv.org/abs/2305.18354)
[^2]: [Enhancing the Building Blocks of Language-Based Visual Reasoning for ARC](https://pub.tik.ee.ethz.ch/students/2023-FS/MA-2023-11.pdf)
[^3]: [Graphs, Constraints, and Search for the Abstraction and Reasoning Corpus](https://arxiv.org/abs/2210.09880)
[^4]: [CodeIt: Self-Improving Language Models with Prioritized Hindsight Replay](https://arxiv.org/abs/2402.04858)
[^5]: [Program Synthesis using Inductive Logic Programming for the Abstraction and Reasoning Corpus](https://arxiv.org/abs/2405.06399)
