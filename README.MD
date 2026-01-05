

RAG (Retrieval, augmentation, generation) frameworks são complexas. Por isso, a abordagem adotada neste projeto é algorítmica e incremental, dividindo o problema em flows. E esses flows são divididos em passo-a-passos.

## O flow número um é o mais simples, é o de ingerir os documentos empresariais.

### Step-by-step
1.1 - O usuário me dá o documento, eu capturo.
1.2 - Eu fatio ele
1.3 - Eu "embedo" ele, converto o texto para algo que a maquina entende
1.4 - Eu jogo no ChromaDB
1.5 - O ChromaDB, indexa, guarda os dados e atual como o banco de vetores. E futuramente disponibiza a semantic search, jeito chique de dizer o texto,vulgo doc mais proximo. 


## O flow número dois é o mais chato, é o que realmente faz o RAG por assim dizer. Ele seria oque faz a  recuperação augmentação e geração.

### Step-by-step
2.1 - O usuário me passa um prompt via uma U.I bem mediocre.
2.2 - Eu embedo esse prompt.
2.3 - Eu faço a semantic search  e pronto fiz o retrieval
2.4 - Eu uso do langchain para me comunicar com uma das milhares de llms por ae. E gero uma versão melhorada do prompt, com os doc retornados da semantic search.
2.5 - Pronto temos uma RAG




Quando um usuário me passar o documento, independente do formato. Eu posso me utilizar do ChromaDB como uma MSE, que faz todo o processo de:
- Embedding
- Indexação
- Ele também disponibiliza o semantic search 



1 - Passo, definir a arquitetura do projeto. E stack
1.0 - Uma RAG, precisa ingerir,indexar. Os documentos repassados, creio que vou ter que usar bibliotecas python para isso.
1.1 - Vou precisar de uma vector embedding database. Vou usar (chromadb)
1.2 - A semantic search também dá para ser feita em (chromadb).
1.3 - A augmentação e a geração podem ser feitas no mesmo passo. Só pegar o prompt e retornar ele com a informação desejada posso usar (langchain comunicando com a llm)
1.4 - V





