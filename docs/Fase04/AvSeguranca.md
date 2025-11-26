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

| Endpoint Testado | Método | Protocolo Identificado  | Cifra | Certificado Válido |
| :--- | :--- | :--- | :--- | :--- |
| /auth/sign_in | POST | HTTPS | 1.3  | Sim |
| /auth/sign_out | DELETE | HTTPS | 1.3  | Sim |
| /auth/sign_up | POST | HTTPS | 1.3  | Sim |
| /auth | PUT | HTTPS | 1.3  | Sim |
| /auth/password | POST | HTTPS | 1.3  | Sim |
| /users/:id | GET | HTTPS | 1.3  | Sim |
| /users/:id | PATCH | HTTPS | 1.3  | Sim |
| /users/:id | DELETE | HTTPS | 1.3  | Sim |
| /users/:user_id/surveys | GET | HTTPS | 1.3  | Sim |
| /users/:user_id/surveys | POST | HTTPS | 1.3  | Sim |
| /users/:user_id/households | GET | HTTPS | 1.3  | Sim |
| /users/:user_id/households | POST | HTTPS | 1.3  | Sim |
| /users/:user_id/households/:id | PATCH | HTTPS | 1.3  | Sim |
| /users/:user_id/households/:id | DELETE | HTTPS | 1.3  | Sim |
| /contents | GET | HTTPS | 1.3  | Sim |
| /apps | GET | HTTPS | 1.3  | Sim |
| /categories | GET | HTTPS | 1.3  | Sim |
| /flexible_answers | POST | HTTPS | 1.3  | Sim |
| /flexible_form_versions | GET | HTTPS | 1.3  | Sim |
| /form_answers | POST | HTTPS | 1.3  | Sim |
| /symptoms | GET | HTTPS | 1.3  | Sim |
| /pre_registers | POST | HTTPS | 1.3  | Sim |

* **Resultado:** (22 / 22) × 100 **100% dos 22 endpoints utilizam HTTPS** 
* **Critério (Alvo):** 100%
* **Status:** **Atingido**
* **Link da Gravação do teste:** [Link Aqui](https://www.youtube.com/watch?v=37ZUvAXiJt8)


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
| Cache Files | **Sim – token** | **Texto Claro** | [Print](https://raw.githubusercontent.com/FCTE-Qualidade-de-Software-1/2025-2_T01_MARLYN-WESCOFF/refs/heads/main/docs/images/evidencia1seguranca.png) |

* **Cálculo:** `(Dados Criptografados / Total Sensíveis) * 100`  
  → `(0 / 1) * 100` = **0%**

* **Critério (Alvo):** ≥ **100%**

* **Status:** **Não Atingido**

---

### 3.4. Métrica SEG-M3.2: Tempo de Descriptografia

**Objetivo:** Avaliar se o processo de descriptografia de dados locais impacta a performance do aplicativo, conforme a hipótese H3.2.  
A métrica verifica se o tempo médio necessário para leitura de informações protegidas (ex.: token criptografado, credenciais armazenadas em contêiner seguro) permanece dentro de um limite aceitável para a usabilidade do usuário.

Como parte da metodologia definida, o tempo de leitura deve ser coletado por meio do **Android Studio Profiler (CPU Profiler)**, medindo especificamente a função responsável pela recuperação e descriptografia dos dados armazenados. O procedimento prevê a coleta de **10 amostras independentes**, executando ações reais do usuário, como:

- abertura do aplicativo,
- carregamento do perfil/logado,
- chamadas internas ao `SecureStorage`.

Como não houve acesso aos dados de execução durante a avaliação, os tempos individuais não puderam ser registrados. Assim, a tabela abaixo é apresentada apenas como estrutura metodológica:

| Amostra | Tempo de Leitura (ms) | Evidência (Profiler) |
| :---: | :---: | :--- |
| Amostra 1 | *Não coletado* | *Indisponível* |

---

### Cálculo
Sem as medições individuais, **não é possível calcular a média** do tempo de descriptografia.

---

### Resultado
- **Média:** *Não calculada*  
- **Critério (Alvo):** ≤ **1s** (1000 ms)  
- **Status:** ⚠️ **Não Avaliado**  
  *A métrica não pôde ser concluída devido à ausência de dados no Profiler durante a execução do teste.*

---

## 4. Integridade (Q4, Q5)

### 4.1. Métrica SEG-M4.1: Alertas de Integridade
**Objetivo:** Verificar se a API rejeita dados manipulados em trânsito (H4.1).

| Cenário de Ataque | Dado Alterado | Resposta da API (HTTP) | Comportamento |
| :--- | :--- | :--- | :--- |
| Modificação de ID em Survey | user_id | 403 Forbidden | Bloqueou |
| Modificação de Timestamp | created_at / timestamp | 422 Unprocessable Entity | Bloqueou |
| Modificação de ID do Próprio Usuário | id | 403 Forbidden | Bloqueou |
| Injeção de Campo Administrativo | admin flag | 403 Forbidden | Bloqueou |
| Modificação de user_id em Household | household user_id | 403 Forbidden | Bloqueou |
| Acesso a Recurso de Outro Usuário | authorization header | 401 Unauthorized | Bloqueou |
| Elevação de Permissão (Role Escalation) | role | 403 Forbidden | Bloqueou |
| Modificação de Status de Formulário | status | 403 Forbidden | Bloqueou |


* **Resultado:** (8 / 8) × 100 = **100%**
* **Critério (Alvo):** Rejeição de 100% das modificações não autorizadas.
* **Status:** **Atingido**
* **Link da Gravação do teste:** [Link Aqui](https://www.youtube.com/watch?v=GT-2iTJAI0s&feature=youtu.be)

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