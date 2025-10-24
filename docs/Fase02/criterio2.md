# Critério 2 — Execução da Avaliação: Adequação Funcional

## 1. Goal (Objetivo) <a href="#ref1"><sup>1</sup></a>

| Elemento | Definição |
|-----------|-----------|
| **Analisar** | o aplicativo *Guardiões da Saúde* |
| **Para o propósito de** | Avaliar |
| **Com respeito a** | *Adequação Funcional* |
| **Do ponto de vista** | 	Desenvolvedores |
| **No contexto da** | Disciplina de Qualidade de Software |

---

## 2. Questions (Questões)
### Perguntas e Hipóteses de Medição

Para estruturar a análise da Adequação Funcional, o objetivo principal foi decomposto nas seguintes perguntas e hipóteses. Cada hipótese formaliza uma premissa sobre o comportamento atual do sistema, cuja validade será aferida por meio de métricas.

## Q1 — Completude Funcional

#### Questão 01: O sistema tem cadastro de usuários completo?

> - **Hipótese 1.1:** O sistema permite criar contas com todos os campos obrigatórios (nome, instituição, matrícula, e-mail e senha).

> - **Hipótese 1.2:** O sistema permite recuperar senha e atualizar dados cadastrais.


## Q2 — Corretude Funcional

#### Questão 02: As funções de cadastro, geolocalização e reporte funcionam corretamente?

> - **Hipótese 2.1:** As funções de cadastro, geolocalização e reporte executam sem falhas críticas ou interrupções.

> - **Hipótese 2.2:** Os dados de saúde (sintomas e localização) são processados sem perda ou duplicação. 

---

## 3. Metrics (Métricas)

## Q1 — Completude Funcional
### M1.1 –  Questão 01:  Hipótese 1.1

!!! info "Detalhes da Métrica"
    - **Objetivo:** medir a taxa de sucesso no Cadastro Completo
    - **Fórmula:**  (Número de cadastros concluídos com sucesso / Total de tentativas de cadastro com todos os campos preenchidos) × 100
    - **Periodicidade:**  semanal 
    - **Valor-alvo:** ≥ 95% 
    - **Coleta:**
    
            1. Analisar os cadastros concluídos com sucesso (contas criadas sem erros).

    - **Responsável:** Equipe de  Desenvolvimento

---

### M1.2 – Questão 01: Hipótese 1.2
!!! info "Detalhes da Métrica"
    - **Objetivo:** medir o tempo de   
    - **Fórmula:**: Σ (tempo entre solicitação e conclusão) / Nº de recuperações
    - **Periodicidade:**  Diario
    - **Valor-alvo:** ≤ 5 minutos
    - **Coleta:** 

            1. Realizar 3 tentativas de recuperação de senha por dia
            2. Registrar o tempo desde o clique em "Esqueci minha senha" até a conclusão da redefinição
            3. Documentar em planilha: data, hora de início, hora de conclusão, tempo total (minutos)
    - **Responsável:** Equipe de  Desenvolvimento

---
  
## Q2 — Corretude  Funcional

### M2.1 – Questão 02: Hipótese 2.1

!!! info "Detalhes da Métrica"
    - **Objetivo:** avaliar a corretude do sistema
    - **Fórmula:**(Nº de operações concluídas sem falhas críticas / Nº total de operações) × 100
    - **Periodicidade:** diária  
    - **Valor-alvo:** ≥ 98%
    - **Coleta:** 

            1. Executar diariamente cada funcionalidade:
                - Cadastro de usuário (2 tentativas)
                - Geolocalização (2 tentativas)
                - Reporte de sintomas (2 tentativas)
            2. Registrar resultado de cada operação: sucesso completo ou falha crítica
            3. Falha crítica = operação não concluída (erro, travamento, timeout)
            4. Documentar em planilha: data, funcionalidade testada, resultado, observações
    - **Responsável:** Equipe de  Desenvolvimento  

---

### M2.2 – Questão 02: Hipótese 2.2


!!! info "Detalhes da Métrica"
    - **Objetivo:**  avaliar a corretude do sistema
    - **Fórmula:** (Nº de registros perdidos / Nº total de registros enviados) × 100
    - **Periodicidade:** diária 
    - **Valor-alvo:**  0% 
    - **Coleta:** 

            1. Acessar relatório com:
            - Total de registros recebidos pela API
            - Total de registros gravados no banco de dados
            - Diferença = registros perdidos
            2. Calcular a métrica com base nos dados fornecidos
    - **Responsável:** Equipes de Desenvolvimento

---

## Diagrama — Adequação Funcional

<div style="width: 640px; height: 480px; margin: 10px; position: relative;"><iframe allowfullscreen frameborder="0" style="width:640px; height:480px" src="https://lucid.app/documents/embedded/6c3136a2-4103-4e5f-946d-27f510706ba4" id="d5GZxvYLtoAL"></iframe></div>
<!--
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


-->
# Referências Bibliográficas

> <a id="ref1"></a> 
>LC03-GQM-Coleta. Disponível em: https://aprender3.unb.br/pluginfile.php/3230283/mod_folder/content/0/LC03-GQM-Coleta.pdf?forcedownload=1. Acesso em: 14 de outubro de 2025.

<a id="ref2"></a> 
>LC04-GQM-Interpretacao. Disponível em: https://aprender3.unb.br/pluginfile.php/3230283/mod_folder/content/0/LC04-GQM-Interpretacao.pdf?forcedownload=1. Acesso em: 14 de outubro de 2025
---

## Histórico de Versões

| Versão | Data | Descrição | Autor | Revisor |
|:------:|:------:|:----------------------------------|:----------------------------------|:-------:|
| 1.0 | 12/10/2025 | Criação do documento inicial e conteúdo | [João Pedro Costa](https://github.com/johnaopedro) | — |
| 1.1 | 14/10/2025 | Adição de referência bibliográfica, questões e diagrama | [Fernanda Vaz Duarte dos Santos](https://github.com/) | — |
| 1.2 | 14/10/2025 | Aprimoramento terminológico e padronização| [Oscar de Brito](https://github.com/OscarDeBrito) | — |
| 1.3 | 15/10/2025 | Adição de Uma Nova Question (Q3)| [Vinícius Rufino](https://github.com/RufinoVfR) | — |
| 1.4 | 16/10/2025 | Remoção da Usabilidade Funcional (Q3) | [João Pedro Costa](https://github.com/johnaopedro) | — |
| 1.5 | 24/10/2025 | Melhora dos topicos e do diagrama | [Fernanda Vaz](https://github.com/Fernandavazgit1) | — |