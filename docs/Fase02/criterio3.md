# Critério 3: Execução da Avaliação - Segurança

## 1. Goal (Objetivo)<a href="#ref1"><sup>1</sup></a>

| Analisar | o aplicativo Guardiões da Saúde |
|----------|--------------------------------|
| Para o propósito de | Controlar e garantir |
| Com respeito a | A segurança com foco em confidencialidade e integridade dos dados de saúde do usuário |
| Do ponto de vista da | Do DPO (Data Protection Officer) e do Arquiteto de Segurança |
| No contexto da | Do manuseio de dados em conformidade com a LGPD |
 

## 2. Questions (Questões)

### Q1: Confidencialidade
Os dados de saúde dos usuários estão efetivamente protegidos contra acesso não autorizado, tanto em repouso quanto em trânsito?

### Q2: Integridade
Existem mecanismos eficazes para garantir que os dados de saúde não sejam alterados ou corrompidos de forma não autorizada?

## 3. Metrics (Métricas)

### M1.1: Número de Incidentes de Acesso Indevido
- **Objetivo:** Monitorar violações de segurança
- **Fórmula:** Contagem de incidentes confirmados por mês
- **Periodicidade:** Mensal
- **Valor Alvo:** 0 incidentes
- **Responsável:** DPO e Equipe de Segurança

### M1.2: Conformidade com Padrões de Criptografia
- **Objetivo:** Garantir a proteção dos dados
- **Fórmula:** (Nº de requisitos de criptografia atendidos / Total de requisitos definidos) * 100
- **Periodicidade:** Trimestral
- **Valor Alvo:** 100%
- **Responsável:** Arquiteto de Segurança

### M2.1: Alertas de Falha na Verificação de Integridade
- **Objetivo:** Identificar tentativas de alteração não autorizada
- **Fórmula:** Número total de alertas de integridade por mês
- **Periodicidade:** Mensal
- **Valor Alvo:** ≤ 5 alertas
- **Responsável:** Equipe de Segurança

### M2.2: Cobertura de Logs de Auditoria
- **Objetivo:** Assegurar rastreabilidade das operações críticas
- **Fórmula:** (Nº de transações críticas com log / Total de transações críticas) * 100
- **Periodicidade:** Semanal
- **Valor Alvo:** ≥ 99.9%
- **Responsável:** Arquiteto de Segurança

## 4. Resultados da Coleta <a href="#ref2"><sup>2</sup></a>

### 4.1 Dados Coletados por Métrica

#### M1.1: Incidentes de Acesso Indevido
- **Período:** [Definir período]
- **Resultado:** [X] incidentes no mês
- **Status:** [Dentro/Fora] do valor alvo (0 incidentes)
- **Tendência:** [Crescente/Decrescente/Estável]

#### M1.2: Conformidade com Criptografia
- **Período:** [Definir período]
- **Resultado:** [X]% de conformidade
- **Status:** [Dentro/Fora] do valor alvo (100%)
- **Tendência:** [Crescente/Decrescente/Estável]

#### M2.1: Alertas de Integridade
- **Período:** [Definir período]
- **Resultado:** [X] alertas no mês
- **Status:** [Dentro/Fora] do valor alvo (≤ 5)
- **Tendência:** [Crescente/Decrescente/Estável]

#### M2.2: Cobertura de Logs
- **Período:** [Definir período]
- **Resultado:** [X]% de cobertura
- **Status:** [Dentro/Fora] do valor alvo (≥ 99.9%)
- **Tendência:** [Crescente/Decrescente/Estável]

## 5. Análise dos Resultados

### 5.1 Confidencialidade
- **Pontos Fortes:**
  1. [Ponto forte 1]
  2. [Ponto forte 2]
- **Pontos de Melhoria:**
  1. [Ponto de melhoria 1]
  2. [Ponto de melhoria 2]

### 5.2 Integridade
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

## Diagrama -  Segurança

<div style="width: 640px; height: 480px; margin: 10px; position: relative;"><iframe allowfullscreen frameborder="0" style="width:640px; height:480px" src="https://lucid.app/documents/embedded/48984a30-effd-49b7-8f39-3fb6ac7ff069" id="l-GZK.nXlew7"></iframe></div>

# Referências Bibliográficas

> <a id="ref1"></a> 
>LC03-GQM-Coleta. Disponível em: https://aprender3.unb.br/pluginfile.php/3230283/mod_folder/content/0/LC03-GQM-Coleta.pdf?forcedownload=1. Acesso em: 14 de outubro de 2025.

<a id="ref2"></a> 
>LC04-GQM-Interpretacao. Disponível em: https://aprender3.unb.br/pluginfile.php/3230283/mod_folder/content/0/LC04-GQM-Interpretacao.pdf?forcedownload=1. Acesso em: 14 de outubro de 2025


## Histórico de Versões

| Versão | Data       | Descrição                                              | Autor                                                                 | Revisor |
|:------:|:----------|:-------------------------------------------------------|:----------------------------------------------------------------------|:-------:|
| 1.0    | 12/10/2025 | Criação do documento inicial e adição do conteúdo      | [João Pedro Costa](https://github.com/johnaopedro)                    | —       |
| 1.1    | 14/10/2025 | Adição de referência bibliográfica| [Fernanda Vaz Duarte dos Santos](https://github.com/)                 | —       |