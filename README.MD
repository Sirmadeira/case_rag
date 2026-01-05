# RAG – Assistente de IA Corporativo

## Visão Geral
Este projeto implementa um **agente de IA corporativo baseado em RAG (Retrieval-Augmented Generation)** sobre o tema **“IA em grandes empresas”**, com foco em qualidade, segurança e práticas de produção.  

## Arquitetura
Uma solução RAG é composta por três etapas principais: **ingestão**, **recuperação** e **geração**.

### 1. Ingestão e Indexação
Os documentos fornecidos (PDF, Word e HTML) são processados utilizando bibliotecas Python específicas para:
- Leitura do conteúdo
- Fragmentação em *chunks*
- Geração de embeddings vetoriais

Cada *chunk* é indexado de forma independente, preservando metadados como fonte e tipo de documento.

### 2. Banco de Vetores e Semantic Search
O **ChromaDB** é utilizado como banco de vetores para:
- Armazenamento dos embeddings
- Execução da busca semântica baseada em similaridade vetorial

A consulta do usuário é convertida em embedding e comparada com os embeddings indexados, retornando os trechos mais relevantes.

### 3. Augmentation e Generation
Os trechos recuperados são utilizados para enriquecer dinamicamente o prompt (*augmentation*).  
A resposta final é gerada por uma **LLM**, com o fluxo orquestrado via **LangChain**, que atua apenas como camada de integração e comunicação de LLMs já disponiveis no mercado.




