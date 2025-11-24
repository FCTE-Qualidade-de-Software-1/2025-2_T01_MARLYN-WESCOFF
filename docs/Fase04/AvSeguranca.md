# Resultados da Avaliação - Segurança

## 1. Introdução
Esta seção detalha os resultados obtidos durante a execução dos testes de segurança no aplicativo e na infraestrutura do **Guardiões da Saúde**. A avaliação seguiu o planejamento definido na Fase 3, cobrindo as subcaracterísticas de **Confidencialidade** e **Integridade**.

## 2. Ambiente de Execução
Os testes foram realizados conforme as especificações abaixo, garantindo a reprodutibilidade dos cenários:

| Item | Detalhe |
| :--- | :--- |
| **Versão do Software** | Guardiões da Saúde (Build de Teste gerada via Android Studio / APK) |
| **Dispositivos** | Emulador Android |
| **Sistema Operacional** | Android 11 |
| **Ferramentas de Apoio** | Gravador de Tela nativo |

---

## 3. Confidencialidade (Q1, Q2, Q3)

### 3.1. Métrica SEG-M1.1: Utilização de HTTPS
**Objetivo:** Verificar se todas as comunicações entre o app e a API utilizam criptografia TLS 1.2+ (H1.1).

| Fluxo Testado | Protocolo Identificado | Certificado Válido? | Link da Evidência (Burp Suite) |
| :--- | :--- | :--- | :--- |
| Login | *[Ex: HTTPS / TLS 1.3]* | *[Sim/Não]* | [Link Aqui] |
| Cadastro | *[Ex: HTTPS / TLS 1.3]* | *[Sim/Não]* | [Link Aqui] |
| Reporte de Sintomas | *[Ex: HTTPS / TLS 1.3]* | *[Sim/Não]* | [Link Aqui] |

* **Resultado:** `(Endpoints Seguros / Total Testados) * 100` = **[X]%**
* **Critério (Alvo):** 100%
* **Status:** *[Atingido / Não Atingido]*

---

### 3.2. Métrica SEG-M2.1: Documentação de Vulnerabilidades
**Objetivo:** Identificar vulnerabilidades no código-fonte através de análise estática (SAST) (H2.1, H2.3).

| Ferramenta | Vulnerabilidades Críticas | Vulnerabilidades Altas | Link do Relatório |
| :--- | :---: | :---: | :--- |
| Snyk (Frontend) | *[Qtd]* | *[Qtd]* | [Link Aqui] |
| Snyk (Backend) | *[Qtd]* | *[Qtd]* | [Link Aqui] |

* **Total Críticas:** **[X]**
* **Critério (Alvo):** 0 Vulnerabilidades Críticas
* **Status:** *[Atingido / Não Atingido]*

---

### 3.3. Métrica SEG-M3.1: Armazenamento Local Seguro
**Objetivo:** Verificar se dados sensíveis (tokens, senhas, PII) estão criptografados no dispositivo (H3.1).

| Arquivo Inspecionado (`adb shell`) | Dado Sensível Encontrado? | Estado (Texto Claro / Criptografado) | Link da Evidência |
| :--- | :--- | :--- | :--- |
| `SharedPreferences` (UserPrefs) | *[Sim/Não]* | *[Ex: Criptografado]* | [Link Aqui] |
| `Databases` (SQLite) | *[Sim/Não]* | *[Ex: Texto Claro]* | [Link Aqui] |
| Cache Files | *[Sim/Não]* | *[Ex: Vazio]* | [Link Aqui] |

* **Cálculo:** `(Dados Criptografados / Total Sensíveis) * 100` = **[X]%**
* **Critério (Alvo):** ≥ 100%
* **Status:** *[Atingido / Não Atingido]*

---

### 3.4. Métrica SEG-M3.2: Tempo de Descriptografia
**Objetivo:** Medir se a segurança impacta a performance (tempo de leitura de dados locais) (H3.2).

| Amostra | Tempo de Leitura (ms) | Link da Evidência (Profiler) |
| :--- | :--- | :--- |
| Amostra 1 | *[Valor]* ms | [Link Aqui] |
| ... | ... | ... |
| Amostra 10 | *[Valor]* ms | [Link Aqui] |

* **Média:** **[X] ms** (ou segundos)
* **Critério (Alvo):** ≤ 1s
* **Status:** *[Atingido / Não Atingido]*

---

## 4. Integridade (Q4, Q5)

### 4.1. Métrica SEG-M4.1: Alertas de Integridade
**Objetivo:** Verificar se a API rejeita dados manipulados em trânsito (H4.1).

| Cenário de Ataque | Dado Alterado | Resposta da API (Código HTTP) | Comportamento (Bloqueou/Aceitou) | Link da Evidência |
| :--- | :--- | :--- | :--- | :--- |
| Manipulação de ID | ID do Usuário na Requisição | *[Ex: 403 Forbidden]* | *[Bloqueou]* | [Link Aqui] |
| Manipulação de Payload | Alteração de Sintomas | *[Ex: 200 OK]* | *[Aceitou - Falha]* | [Link Aqui] |

* **Resultado:** O mecanismo de integridade funcionou? **[Sim/Não]**
* **Critério (Alvo):** Rejeição de modificações não autorizadas.
* **Status:** *[Atingido / Não Atingido]*

---

### 4.2. Métrica SEG-M5.1: Rastreabilidade de Operações
**Objetivo:** Assegurar que operações críticas geram logs de auditoria no backend (H5.1).

| Operação Crítica | Log Gerado? | Conteúdo do Log (UserID, Timestamp, IP) | Link da Evidência |
| :--- | :--- | :--- | :--- |
| Login | *[Sim/Não]* | *[Completo/Incompleto]* | [Link Aqui] |
| Reporte de Saúde | *[Sim/Não]* | *[Completo/Incompleto]* | [Link Aqui] |
| Alteração de Perfil | *[Sim/Não]* | *[Completo/Incompleto]* | [Link Aqui] |

* **Cálculo:** `(Ops com Log Completo / Ops Testadas) * 100` = **[X]%**
* **Critério (Alvo):** 100%
* **Status:** *[Atingido / Não Atingido]*

---

## 5. Análise Global e Julgamento

A classificação abaixo segue rigorosamente os Níveis de Pontuação definidos na Fase 2.

### 5.1. Classificação das Métricas

| ID | Métrica | Valor Obtido | Nota Equiv. (0-10) | Nível (Classificação) | Justificativa |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **SEG-M1.1** | HTTPS | *[Preencher]* | *[Nota]* | *[Definir]* | *[Justificativa]* |
| **SEG-M2.1** | Vulnerabilidades | *[Preencher]* | *[Nota]* | *[Definir]* | *[Justificativa]* |
| **SEG-M3.1** | Armaz. Local | *[Preencher]* | *[Nota]* | *[Definir]* | *[Justificativa]* |
| **SEG-M3.2** | Descriptografia | *[Preencher]* | *[Nota]* | *[Definir]* | *[Justificativa]* |
| **SEG-M4.1** | Integridade | *[Preencher]* | *[Nota]* | *[Definir]* | *[Justificativa]* |
| **SEG-M5.1** | Rastreabilidade | *[Preencher]* | *[Nota]* | *[Definir]* | *[Justificativa]* |

### 5.2. Julgamento da Característica: Segurança

Para determinar o resultado final, aplicam-se os seguintes critérios:

* **Aceitável:** > 70% das métricas classificadas como *Bom* ou *Excelente*.
* **Parcialmente Aceitável:** < 35% das métricas atingindo *Insuficiente*.
* **Inaceitável:** >= 35% das métricas atingindo *Insuficiente*.

> **Parecer Preliminar:** *[Inserir análise final. Exemplo: O sistema garante confidencialidade no tráfego (HTTPS), mas apresenta riscos no armazenamento local de credenciais, exigindo correção imediata para atingir o nível Aceitável.]*

---

## Declaração do uso de Inteligência Artificial

\<p style="text-indent:30px; text-align: justify"\>Durante o desenvolvimento deste relatório, foi utilizada a ferramenta de Inteligência Artificial (Gemini) para a estruturação das tabelas de resultados e consolidação das hipóteses definidas nas fases anteriores. Todas as informações, referências e interpretações técnicas foram validadas e ajustadas manualmente pela equipe após a execução dos testes, garantindo a precisão e a coerência com o contexto real do projeto Guardiões da Saúde.\</p\>

## Referências

> 1.  Equipe Marlyn Wescoff. **Critério 2 — Execução da Avaliação: Adequação Funcional**. Fase 2 do Projeto de Qualidade de Software. Disponível no repositório do projeto.

> 2.  Equipe Marlyn Wescoff. **Critério 3 — Execução da Avaliação: Segurança**. Fase 2 do Projeto de Qualidade de Software. Disponível no repositório do projeto.

> 3.  Equipe Marlyn Wescoff. **Níveis de Pontuação e Critérios de Julgamento**. Fase 2 do Projeto de Qualidade de Software. Disponível no repositório do projeto.

## Histórico de Versão

| Versão | Data       | Descrição                         | Autor                               | Revisor |
|:------:|:----------|:----------------------------------|:-------------------------------------|:-------:|
| 1.0    | 24/11/2025 | Criação do Documento inicial e elaboração do documento | [João Pedro Costa](https://github.com/johnaopedro) |   —    |