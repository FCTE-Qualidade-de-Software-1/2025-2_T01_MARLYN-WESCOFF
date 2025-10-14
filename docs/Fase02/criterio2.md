# Critério 2: Execução da Avaliação - Adequação Funcional 

## 1. Goal (Objetivo)<a href="#ref1"><sup>1</sup></a>

| Analisar               | o aplicativo Guardiões da Saúde |
|------------------------|--------------------------------|
| Para o propósito de    | Avaliar e melhorar            |
| Com respeito a         | A adequação funcional com foco em sua completude e corretude funcional |
| Do ponto de vista da   | Da equipe de 	Equipe de desenvolvimento     |
| No contexto da         | Disciplina de Qualidade de Software  (FCTE - UnB) |


## 2. Questions (Questões)
### Perguntas e Hipóteses de Medição

Para estruturar a análise da Adequação Funcional, o objetivo principal foi decomposto nas seguintes perguntas e hipóteses. Cada hipótese formaliza uma premissa sobre o comportamento atual do sistema, cuja validade será aferida por meio de métricas.


#### Questão 01: O sistema dos Guardiões da Saúde oferece todas as funcionalidades necessárias para cadastro e gestão de usuários?
> - **Hipótese 1.1:** O sistema permite criar contas de usuário com todos os campos obrigatórios (nome, Nome da instituição de ensino, matrícula,e-mail e senha) sem erros.

> - **Hipótese 1.2:** O sistema permite recuperação de senha e atualização de dados cadastrais.

#### Questão 02: O sistema dos Guardiões da Saúde  permite relatar todos os tipos de sintomas relevantes para vigilância epidemiológica? 

> - **Hipótese 2.1:** O sistema possui um formulário completo para registro de sintomas recomendados pelo órgão de vigilância

> - **Hipótese 2.2:**  O sistema permite adicionar sintomas adicionais não pré-definidos, garantindo flexibilidade.


> - **Hipótese 2.3:** O sistema registra corretamente os sintomas relatados e os associa ao usuário que reportou.


#### Questão 03: O sistema dos Guardiões da Saúde  O sistema captura todas as informações de localização necessárias para vigilância epidemiológica?
> - **Hipótese 3.1:** O sistema solicita permissão do usuário para acesso à localização e só coleta dados com consentimento.

> - **Hipótese 3.2:** O sistema permite registrar localização manual caso o GPS não esteja disponível.

> - **Hipótese 3.3:** O sistema utiliza dados precisos, como município e cidade, para ter uma precisão mais elevada.


#### Questão 04: O sistema dos Guardiões da Saúde  mantém consistência entre múltiplos relatos do mesmo usuário ao longo do tempo?
> - **Hipótese 4.1:** O sistema permite que um mesmo usuário faça múltiplos relatos de sintomas em datas diferentes.

> - **Hipótese 4.2:** O sistema mantém histórico completo de todos os relatos anteriores do usuário, permitindo rastreamento temporal.

> - **Hipótese 4.3:** O sistema impede que usuários editem ou excluam relatos já submetidos, garantindo integridade dos dados históricos.



### Q2: Corretude Funcional
As funções de cadastro e reporte processam as entradas, executam as operações e geram os resultados corretos, sem falhas?

## 3. Metrics (Métricas)

### M1.1: Percentual de Requisitos Funcionais Essenciais (RFE) implementados
- **Objetivo:** Medir a completude da implementação dos requisitos essenciais
- **Fórmula:** (Nº de RFE implementados / Nº total de RFE definidos) * 100
- **Periodicidade:** Mensal
- **Valor Alvo:** ≥ 95%
- **Responsável:** Equipe de QA

### M2.1: Taxa de Erro nas Transações de Reporte de Saúde
- **Objetivo:** Avaliar a confiabilidade das operações de reporte
- **Fórmula:** (Nº de reportes com falha / Nº total de tentativas de reporte) * 100
- **Periodicidade:** Diária
- **Valor Alvo:** ≤ 1%
- **Responsável:** Equipe de QA

### M2.2: Densidade de Defeitos em Produção
- **Objetivo:** Mensurar a qualidade funcional em ambiente de produção
- **Fórmula:** Nº de bugs críticos/altos reportados / Tamanho ou nº de usuários ativos
- **Periodicidade:** Mensal
- **Valor Alvo:** ≤ 0.01 (1 bug crítico/alto para cada 100 usuários ativos)
- **Responsável:** Equipe de QA e Produto

## 4. Resultados da Coleta <a href="#ref2"><sup>2</sup></a>

### 4.1 Dados Coletados por Métrica

#### M1.1: Percentual de RFE implementados
- **Período:** [Definir período]
- **Resultado:** [X]% de requisitos implementados
- **Status:** [Dentro/Fora] do valor alvo (≥ 95%)
- **Tendência:** [Crescente/Decrescente/Estável]

#### M2.1: Taxa de Erro nas Transações
- **Período:** [Definir período]
- **Resultado:** [X]% de falhas em reportes
- **Status:** [Dentro/Fora] do valor alvo (≤ 1%)
- **Tendência:** [Crescente/Decrescente/Estável]

#### M2.2: Densidade de Defeitos
- **Período:** [Definir período]
- **Resultado:** [X] bugs por 100 usuários
- **Status:** [Dentro/Fora] do valor alvo (≤ 0.01)
- **Tendência:** [Crescente/Decrescente/Estável]

## 5. Análise dos Resultados

### 5.1 Completude Funcional
- **Pontos Fortes:**
  1. [Ponto forte 1]
  2. [Ponto forte 2]
- **Pontos de Melhoria:**
  1. [Ponto de melhoria 1]
  2. [Ponto de melhoria 2]

### 5.2 Corretude Funcional
- **Pontos Fortes:**
  1. [Ponto forte 1]
  2. [Ponto forte 2]
- **Pontos de Melhoria:**
  1. [Ponto de melhoria 1]
  2. [Ponto de melhoria 2]

## 6. Ações de Melhoria

1. xxxxxxxxxxxx
2. xxxxxxxxxxxx
3. xxxxxxxxxxxx

## Diagrama - Adequação Funcional 
<div style="width: 640px; height: 480px; margin: 10px; position: relative;"><iframe allowfullscreen frameborder="0" style="width:640px; height:480px" src="https://lucid.app/documents/embedded/6c3136a2-4103-4e5f-946d-27f510706ba4" id="d5GZxvYLtoAL"></iframe></div>

# Referências Bibliográficas

> <a id="ref1"></a> 
>LC03-GQM-Coleta. Disponível em: https://aprender3.unb.br/pluginfile.php/3230283/mod_folder/content/0/LC03-GQM-Coleta.pdf?forcedownload=1. Acesso em: 14 de outubro de 2025.

<a id="ref2"></a> 
>LC04-GQM-Interpretacao. Disponível em: https://aprender3.unb.br/pluginfile.php/3230283/mod_folder/content/0/LC04-GQM-Interpretacao.pdf?forcedownload=1. Acesso em: 14 de outubro de 2025

## Histórico de Versões

| Versão | Data       | Descrição                                              | Autor                                                                 | Revisor |
|:------:|:----------|:-------------------------------------------------------|:----------------------------------------------------------------------|:-------:|
| 1.0    | 12/10/2025 | Criação do documento inicial e adição do conteúdo      | [João Pedro Costa](https://github.com/johnaopedro)                    | —       |
| 1.1    | 14/10/2025 | Adição de referência bibliográfica, questões e diagrama | [Fernanda Vaz Duarte dos Santos](https://github.com/)                 | —       |