# Consolidado Prático — Aula 05b Parte D

## Parte 1: Síntese dos Módulos 10 a 12
* **Módulo 10:** Construção e exportação do ficheiro `qrels.csv` com base nas 3 consultas do corpus dos municípios da Baixada Santista. Aplicação do pooling e definição do vetor nomeado de graus de relevância reais.
* **Módulo 11:** Implementação das funções de cálculo para as 5 métricas de avaliação (P@3, AP, MRR, nDCG bin e nDCG grad), garantindo o tratamento de documentos não julgados como grau 0.
* **Módulo 12:** Execução da avaliação em todas as consultas (`q01`, `q02`, `q03`), cálculo da métrica agregada MAP (Mean Average Precision) e análise crítica dos resultados obtidos.

## Parte 2: Ficha do Aluno
* **Escolha do Limiar:** Escolheu o limiar `grau >= 2` para a classificação de documentos relevantes no gabarito real.
* **Tratamento de Não Julgados:** Aplicou a atribuição explicita de valor 0 para documentos ausentes do pooling.
* **Análise do Vencedor:** Registou o empate técnico perfeito entre os dois modelos e identificou a limitação do tamanho da coleção como causa da falta de discriminação métrica.

## Parte 3: Produzido
* **Limiar:** `grau >= 2`
* **Tabela-Resumo por Consulta:**

| Consulta | Texto | AP Cosseno | AP BM25 | Vencedor |
|---|---|---|---|---|
| **q01** | café museu | 1.000 | 1.000 | Empate |
| **q02** | fortaleza artilharia | 1.000 | 1.000 | Empate |
| **q03** | fundação primeira cidade | 1.000 | 1.000 | Empate |

* **MAP dos Sistemas:** Cosseno = 1.000 | BM25 = 1.000
* **Ressalva do Aluno:** O corpus reduzido (3 documentos) faz com que ambos os modelos recuperem o documento ideal na primeira posição, resultando num MAP de 1,000 para ambos os sistemas. Não é possível afirmar a superioridade de nenhum dos dois sem ampliar o tamanho da base de documentos ou das consultas.