# Critério 2 — Execução da Avaliação: Adequação Funcional

## 1. Goal (Objetivo) [^1]

| Elemento | Definição |
|-----------|-----------|
| **Analisar** | o aplicativo *Guardiões da Saúde* |
| **Para o propósito de** | Garantir e caracterizar sua qualidade funcional |
| **Com respeito a** | *Adequação Funcional*, com foco em *Completude* e *Corretude Funcional* |
| **Do ponto de vista** | da equipe de Produto e Garantia da Qualidade (QA) |
| **No contexto da** | Disciplina de Qualidade de Software |

---

## 2. Questions (Questões)

### Questão 1: Completude Funcional

1.  **Hipótese 1.1 (H1.1):** Todas as funções críticas (cadastro, autenticação, relato de sintomas e geolocalização) estão implementadas e acessíveis no aplicativo.  
2. **Q1.2 – Notificação de Sintomas:** o aplicativo contempla todos os tipos de sintomas relevantes para a vigilância epidemiológica?  
3. **Q1.3 – Geolocalização e Contexto:** o sistema captura e transmite corretamente as informações de localização necessárias ao monitoramento epidemiológico?  

### Q2 — Corretude Funcional

As funções implementadas produzem resultados corretos e consistentes?

4. **Q2.1 – Processamento das Operações:** as funções de cadastro, geolocalização e reporte processam as entradas, executam as operações e retornam resultados corretos, sem falhas ou inconsistências?  
5. **Q1.2 – Notificação de Sintomas:** O processamento dos dados de saúde (sintomas e localização) ocorre sem perda ou duplicação de registros. 

---

## 3. Metrics (Métricas)

### M1.1 – Percentual de Requisitos Funcionais Essenciais (RFE) Implementados

!!! info "Detalhes da Métrica"
    - **Objetivo:** medir o grau de completude das funcionalidades críticas previstas nos requisitos.  
    - **Fórmula:** (Nº de RFE implementados / Nº total de RFE definidos) × 100  
    - **Periodicidade:** mensal  
    - **Valor-alvo:** ≥ 95 %  
    - **Responsável:** Equipe de QA  

---

### M2.1 – Taxa de Erro nas Transações de Reporte de Saúde

!!! info "Detalhes da Métrica"
    - **Objetivo:** avaliar a confiabilidade do processo de envio de sintomas.  
    - **Fórmula:** (Nº de reportes com falha / Nº total de tentativas de reporte) × 100  
    - **Periodicidade:** diária  
    - **Valor-alvo:** ≤ 1 %  
    - **Responsável:** Equipe de QA  

---

### M2.2 – Densidade de Defeitos em Produção

!!! info "Detalhes da Métrica"
    - **Objetivo:** mensurar a incidência de defeitos críticos que afetam a corretude funcional.  
    - **Fórmula:** Nº de bugs críticos ou altos reportados / Nº de usuários ativos × 100  
    - **Periodicidade:** mensal  
    - **Valor-alvo:** ≤ 0,01 (1 defeito crítico a cada 100 usuários ativos)  
    - **Responsável:** Equipes de Produto e QA  

---

## 4. Resultados da Coleta [^2]

| Métrica | Período | Resultado | Status | Tendência |
|----------|----------|-----------|---------|-----------|
| **M1.1 – RFE implementados** | [definir] | [X]% | [dentro/fora do alvo ≥ 95 %] | [crescente/decrescente/estável] |
| **M2.1 – Taxa de erro em reportes** | [definir] | [X]% | [dentro/fora do alvo ≤ 1 %] | [crescente/decrescente/estável] |
| **M2.2 – Densidade de defeitos** | [definir] | [X] bugs / 100 usuários | [dentro/fora do alvo ≤ 0,01] | [crescente/decrescente/estável] |

---

## 5. Análise dos Resultados

### 5.1 Completude Funcional

!!! success "Pontos Fortes"
    1. Cobertura ampla dos fluxos principais (cadastro, geolocalização, reporte).  
    2. Alta taxa de aderência aos requisitos funcionais documentados.  

!!! warning "Pontos de Melhoria"
    1. Revisar funcionalidades secundárias ausentes (ex.: histórico detalhado de sintomas).  
    2. Aperfeiçoar a integração entre módulos de cadastro e notificação.  

---

### 5.2 Corretude Funcional

!!! success "Pontos Fortes"
    1. Processamento correto dos reportes e consistência entre app e API.  
    2. Baixo índice de falhas de transação (< 1 %).  

!!! warning "Pontos de Melhoria"
    1. Automatizar testes de regressão para prevenir erros funcionais recorrentes.  
    2. Refinar mensagens de erro e logs para rastreabilidade mais precisa.  

---

## 6. Ações de Melhoria

1. Revisar documentação de requisitos e atualizar o checklist de RFE.  
2. Ampliar a cobertura de testes automatizados de integração (frontend ↔ API).  
3. Implementar pipeline de monitoramento contínuo de falhas em produção.  

---

## Diagrama — Adequação Funcional

<div style="width: 640px; height: 480px; margin: 10px; position: relative;"><iframe allowfullscreen frameborder="0" style="width:640px; height:480px" src="https://lucid.app/documents/embedded/6c3136a2-4103-4e5f-946d-27f510706ba4" id="d5GZxvYLtoAL"></iframe></div>

# Referências Bibliográficas

> <a id="ref1"></a> 
>LC03-GQM-Coleta. Disponível em: https://aprender3.unb.br/pluginfile.php/3230283/mod_folder/content/0/LC03-GQM-Coleta.pdf?forcedownload=1. Acesso em: 14 de outubro de 2025.

<a id="ref2"></a> 
>LC04-GQM-Interpretacao. Disponível em: https://aprender3.unb.br/pluginfile.php/3230283/mod_folder/content/0/LC04-GQM-Interpretacao.pdf?forcedownload=1. Acesso em: 14 de outubro de 2025
---

## Histórico de Versões

| Versão | Data | Descrição | Autor | Revisor |
|:------:|:------:|:----------------------------------|:----------------------------------|:-------:|
| 1.0 | 12/10/2025 | Criação do documento inicial | [João Pedro Costa](https://github.com/johnaopedro) | — |
| 1.1 | 14/10/2025 | Revisão técnica, refinamento das questões e métricas | [Fernanda Vaz Duarte dos Santos](https://github.com/) | — |
| 1.2 | 14/10/2025 | Aprimoramento terminológico e padronização| [Oscar de Brito](https://github.com/OscarDeBrito) | — |
