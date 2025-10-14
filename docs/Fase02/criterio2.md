# Critério 2: Execução da Avaliação - Adequação Funcional 

## 1. Goal (Objetivo)<a href="#ref1"><sup>1</sup></a>

| Analisar               | o aplicativo Guardiões da Saúde |
|------------------------|--------------------------------|
| Para o propósito de    | Garantir e melhorar            |
| Com respeito a         | A adequação funcional com foco em sua completude e corretude funcional |
| Do ponto de vista da   | Da equipe de Produto e QA      |
| No contexto da         | Da operação contínua do aplicativo |


## 2. Questions (Questões)

### Q1: Completude Funcional
**Q1.1: Cadastro e Autenticação**:
O sistema oferece todas as funcionalidades necessárias para cadastro e gestão de usuários?
**Q1.2: Notificação de Sintomas**
O sistema permite relatar todos os tipos de sintomas relevantes para vigilância epidemiológica?
**Q1.3: Geolocalização e Contexto**
O sistema captura todas as informações de localização necessárias para vigilância epidemiológica?

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
| 1.1    | 14/10/2025 | Adição de referência bibliográfica e questões| [Fernanda Vaz Duarte dos Santos](https://github.com/)                 | —       |