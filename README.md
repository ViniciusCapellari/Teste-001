Integrantes da dupla: Guilherme Menezes RA 1134714 e Vinicius Gehring Capellari 1138972
README.md
Projeto de Pré-processamento de Dados – Mobilidade Urbana
Disciplina: Pensamento Computacional / Pandas
1. Contexto do Projeto
Este projeto simula uma etapa real de pré-processamento de dados em um fluxo de Data Science.
O dataset utilizado contém respostas coletadas em uma pesquisa sobre mobilidade urbana, com várias colunas textuais e pouco estruturadas.
Nosso objetivo foi aplicar lógica de programação e Pandas para transformar uma coluna textual em um valor numérico útil, tornando o dataset adequado para análises estatísticas e visualizações.

2. Dataset Utilizado
Arquivo: Pesquisa sobre Mobilidade Urbana (CSV convertido do PDF original)
Fonte: fornecido pelo Professor Me. Fernando Posser, disponível em AVA/Atitus. 
A coluna selecionada para transformação foi:
“Quais fatores mais te incomodam no trânsito? (escolha até 3)”, correspondente a coluna K. 
Essa coluna contém múltiplos itens textuais separados por ponto e vírgula, o que impede análises quantitativas diretas.

3. Problema Identificado
A coluna apresenta desafios como:
Múltiplas categorias por célula
Valores exclusivamente textuais
Ausência de padronização
Impossibilidade de calcular frequências, médias ou rankings diretamente


Exemplo de resposta original:
"Tempo perdido;Estresse;Custo com combustível"

Para análise, é necessário transformar essas respostas textuais em valores numéricos consistentes.

4. Solução Desenvolvida
Criamos uma função Python para:
Limpar o texto


Separar itens por “;”


Mapear cada fator para um número


Gerar um valor numérico final (via soma dos fatores)


Mapeamento utilizado (exemplo):
Fator
Código
Tempo perdido
1
Estresse
2
Custo com combustível
3
Insegurança
4
Poluição
5
Outros
6

Lógica da função:
Recebe a string da coluna
Divide os itens
Padroniza
Converte cada item para o número correspondente
Retorna a soma dos códigos, criando um indicador numérico total


Aplicação no Pandas:
df["incomodos_numericos"] = df["Quais fatores mais te incomodam no trânsito? (escolha até 3)"].apply(transformar_incomodos)

5. Impacto da Transformação
Com a coluna numérica criada, foi possível:
Identificar quais incômodos são mais frequentes
Comparar incômodos entre faixas etárias
Analisar diferenças entre meios de transporte
Criar gráficos e rankings
Observar padrões de irritação no trânsito


Exemplos de análises feitas no notebook:
Contagem dos incômodos mais citados
Relação entre renda mensal e nível de incômodo - estudos futuros
Comparação entre motoristas e usuários de transporte público - estudos futuros

6. Arquivos Entregues
O repositório contém:
dataset.csv – arquivo utilizado
Escopo do projeto completo
notebook.ipynb – código completo da transformação, análise e visualizações
README.md – explicação do projeto


7. Conclusões
O Data science utiliza técnicas científicas consolidadas de processamento de dados - seja via estatística, machine learning e outros que permitem abordar problemas (questões não resolvidas) de maneira abrangente, sistêmica e eficaz. 
No estudo em questão os dados estavam pré-tabulados, porém sem os devidos tratamentos, o que impedia análises estatísticas das respostas existentes. Além disso, a automatização através da criação de uma função de transformação em Python permitiria, entre outras coisas, aumentar a escala do trabalho, na medida em que consiste em uma automatização parcial do esforço de pesquisa realizado. 
Neste sentido, o trabalho reforça a importância do pré-processamento em Data Science e da conversão de dados brutos em tratáveis para posterior conversão destes em informações para tomada de decisões. 
Percebe-se ainda que transformar dados textuais em valores numéricos abre espaço para análises mais profundas, confiáveis e consistentes e visualizações que auxiliam na interpretação dos fenômenos, neste caso, urbanos.

