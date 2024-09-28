# MigNar Benchmark

This repo contains the code and dataset pertaining to MigNar - a benchmark dataset which leverages recent advances in generative transformer-based large language models (LLMs) to simulate ground truth in a corpus of synthetically generated articles on Brexit and migration. The generative architecture is as follows: 

![alt text](https://github.com/tediyankov/mignar-benchmark/blob/main/mignar_gen.png.jpg?raw=true)

1. Start with a prompt template. At this stage, the prompt employs two-shot learning (2SL) by providing two examples using different parameter combinations.
2. A random draw is made from a distribution of narratives on migration.
3. A random draw is made from a distribution of UK publications. Context for this is taught to the LLM via 2SL.
4. A random draw is made from a continuous distribution of passion level scores (from 0-10 where 0 is neutral and 10 is fiery), and language complexity (where 0 is simple text and 10 is academic writing). Context for this is taught to the LLM via 2SL.
5. The filled-in prompt is passed to the generative LLM to produce the article text.
6. The output is stored in the MigNar corpus in tabular format, alongside columns
containing the parameter combination used to generate that specific article.
7. The process is repeated 600 times (300 times for antagonistic narratives and 300
times for protagonistic ones).
