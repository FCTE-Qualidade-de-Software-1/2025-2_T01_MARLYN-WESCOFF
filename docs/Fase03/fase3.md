# Fase 03 - Plano de Execução da Avaliação (Guardiões da Saúde)

### **1. Introdução**

Este documento descreve o plano detalhado de execução da avaliação do sistema **Guardiões da Saúde**, seguindo a metodologia GQM (Goal-Question-Metric) estabelecida na Fase 2. O foco deste plano é operacionalizar a coleta de dados, servindo como guia para a **Fase 04 (Execução dos Casos de Teste)**.

O escopo da avaliação, definido na Fase 1, foca nas características de **Adequação Funcional** (Completude e Corretude) e **Segurança** (Confidencialidade e Integridade), conforme o modelo de qualidade ISO/IEC 25010. Os objetos de avaliação são o aplicativo cliente, o repositório do frontend e o repositório do backend.

### **2. Objetivos da Fase 3**

* Operacionalizar as métricas definidas na Fase 2 em procedimentos executáveis (que serão detalhados como Casos de Teste na Fase 4).
* Estabelecer critérios claros para a coleta e análise de evidências.
* Definir o ambiente, as ferramentas e os artefatos necessários para a execução.
* Garantir a rastreabilidade entre os objetivos (Fase 2), este plano (Fase 3) e os testes (Fase 4).
* Fornecer um guia completo para a execução consistente da avaliação.

### **3. Visão Geral**

Este documento descreve *como* executar a avaliação (passo a passo) para obter as medidas definidas na Fase 2. Ele detalha como registrar evidências, calcular métricas e aplicar os critérios de julgamento. O plano está organizado por métrica: para cada uma, são definidos objetivos, passos de execução, entradas/saídas, evidências exigidas e como calcular/julgar o resultado.

### **4. Metodologia de Avaliação**

A avaliação seguirá uma abordagem sistemática baseada em:

* **Testes funcionais (caixa-preta):** Para métricas de adequação funcional.
* **Análise de código (caixa-branca):** Para métricas de segurança (ex: M2.1 - SAST).
* **Testes de segurança (caixa-cinza):** Para análise de tráfego (M1.1) e armazenamento local (M3.1).
* **Coleta sistemática de evidências objetivas:** Logs, screenshots, relatórios de ferramentas.

#### **4.1. Princípios de Avaliação**

* **Reprodutibilidade:** Todos os testes definidos na Fase 4 devem ser replicáveis.
* **Objetividade:** As evidências devem ser mensuráveis e verificáveis.
* **Transparência:** Processos e critérios claramente documentados.
* **Consistência:** Aplicação uniforme dos critérios de julgamento.

#### **4.2. Instruções Gerais Para o Avaliador**

* **Antes de iniciar:**
    * Verificar se o ambiente está configurado conforme descrito na Seção 5.
    * Garantir que as ferramentas (Android Studio, ADB, Burp Suite, Snyk) estão instaladas.
    * Ter acesso aos templates de registro de resultados.
* **Durante a execução:**
    * Capturar evidências sempre que solicitado (screenshots, logs de console, logs de proxy).
    * Registrar tudo, mesmo erros inesperados ou dúvidas.
* **Após a execução:**
    * Garantir que toda evidência está armazenada corretamente.
    * Preencher a planilha de resultados de forma completa.

---

### **5. Preparação (Artefatos e Templates Necessários)**

#### **5.1. Documentação de Suporte**

* **Templates de Caso de Teste (para Fase 4):** Estrutura padrão (ID, Métrica, Objetivo, Passos, Entradas, Saída Esperada).
* **Checklist de evidências:** (print screens, logs do ADB, logs de proxy, relatórios SAST).

#### **5.2. Ambiente de Teste**

* **Objetos de Avaliação:**
    * Aplicativo cliente (Google Play Store).
    * Repositório open source (Frontend - `guardioes-app`).
    * Repositório open source (Backend - `guardioes-api`).
* **Sistemas Operacionais:** Android 12+ (Emulador) e Android 14 (Dispositivo Físico).
* **Backend:** Instância local da API (`guardioes-api`) rodando via Docker para testes controlados.
* **Ferramentas de Análise:**
    * Android Studio (Profiler, Logcat).
    * `adb` (Android Debug Bridge).
    * Ferramenta de Proxy: Burp Suite ou OWASP ZAP.
    * Ferramenta SAST: Snyk ou GitHub CodeQL.
    * Cliente de Banco de Dados (ex: DBeaver).

---

### **6. Procedimento Geral de Execução (Válido para Fase 4)**

1.  **Preparação:** Ler o Caso de Teste (CT) na Fase 4 e a métrica correspondente na Fase 2.
2.  **Planejamento:** Preparar a massa de dados e o ambiente específico do CT.
3.  **Execução:** Executar o(s) teste(s) seguindo os passos numerados no CT.
4.  **Registro:** Registrar os resultados na planilha padrão, incluindo a evidência.
5.  **Classificação:** Marcar a execução do CT como: Sucesso, Parcial, Falha.
6.  **Cálculo (Pós-execução):** Ao final dos CTs, calcular a fórmula da métrica.
7.  **Conclusão (Pós-execução):** Registrar a conclusão da métrica (Atende / Parcial / Não atende) com base nos critérios.

---

### **7. Plano por Métrica — Adequação Funcional**

Baseado no GQM da Fase 2.

#### **7.1. M1.1 — Taxa de Sucesso no Cadastro Completo**
* **Objetivo:** Medir a taxa de sucesso no Cadastro Completo (para H1.1).
* **Passos de Execução:**
    1.  Preparar 10 massas de dados de teste (novos usuários) com todos os campos obrigatórios.
    2.  Executar 10 tentativas de cadastro no aplicativo.
    3.  Registrar 'Sucesso' (conta criada sem erros) ou 'Falha'.
    4.  Verificar no backend (banco de dados) se o usuário foi persistido corretamente.
* **Evidência:** Planilha de execução (Sucesso/Falha), screenshots de erro, query no BD.
* **Cálculo:** `(Número de cadastros concluídos com sucesso / Total de tentativas de cadastro com todos os campos preenchidos) × 100`.
* **Critério (Valor-alvo):** ≥ 95%.

#### **7.2. M1.2 — Tempo de Recuperação de Senha**
* **Objetivo:** Medir o tempo de recuperação de senha (para H1.2).
* **Passos de Execução:**
    1.  Realizar 3 tentativas de recuperação de senha por dia para contas de teste válidas.
    2.  Iniciar o cronômetro ao clicar em "Esqueci minha senha" e submeter o e-mail.
    3.  Parar o cronômetro quando a redefinição for concluída (ex: e-mail recebido e senha alterada).
    4.  Documentar em planilha: data, hora de início, hora de conclusão, tempo total (minutos).
* **Evidência:** Planilha com timestamps, screenshots dos e-mails.
* **Cálculo:** `Σ (tempo entre solicitação e conclusão) / Nº de recuperações`.
* **Critério (Valor-alvo):** ≤ 5 minutos.

#### **7.3. M2.1 — Taxa de Sucesso de Operações Principais**
* **Objetivo:** Avaliar a corretude do sistema (para H2.1).
* **Passos de Execução:**
    1.  Executar cada funcionalidade 3 vezes.
    2.  Registrar resultado: 'Sucesso' ou 'Falha Crítica'.
    3.  (Definição de Falha Crítica: operação não concluída, erro, travamento, timeout).
    4.  Documentar em planilha: data, funcionalidade, resultado, observações.
* **Evidência:** Screenshots de erro ou vídeo.
* **Cálculo:** `(Nº de operações concluídas sem falhas críticas / Nº total de operações) × 100`.
* **Critério (Valor-alvo):** ≥ 98%.

#### **7.4. M2.2 — Taxa de Perda de Registros de Saúde**
* **Objetivo:** Avaliar a corretude do processamento de dados (para H2.2).
* **Passos de Execução:**
    1.  Enviar 50 reportes de sintomas distintos (massa de teste) usando o App.
    2.  Acessar o backend (API e banco de dados).
    3.  Verificar o total de registros recebidos pela API (via log da API).
    4.  Verificar o total de registros gravados no banco de dados (via query SQL).
    5.  Calcular a diferença (registros perdidos).
* **Evidência:** Logs da API (contagem de `POST`), resultado da query SQL.
* **Cálculo:** `(Nº de registros perdidos / Nº total de registros enviados) × 100`.
* **Critério (Valor-alvo):** 0%.

---

### **8. Plano por Métrica — Segurança**

Baseado no GQM da Fase 2.

#### **8.1. M1.1 — Utilização de HTTPS**
* **Objetivo:** Verificar se todas as comunicações utilizam HTTPS/TLS (para Q1/H1.1).
* **Passos de Execução:**
    1.  Configurar um proxy de interceptação (Burp Suite) no dispositivo de teste.
    2.  Executar todos os fluxos do app (Login, Cadastro, Reporte).
    3.  Analisar o log de tráfego no Burp Suite.
    4.  Verificar se 100% das requisições para a API são HTTPS.
    5.  Confirmar protocolos suportados (TLS 1.2 ou superior) e certificados válidos.
* **Evidência:** Logs do Burp Suite, screenshots da análise do certificado.
* **Cálculo:** (Fórmula `???`) Será: `(Nº de endpoints da API usando HTTPS / Total de endpoints testados) × 100`.
* **Critério (Valor-alvo):** 100% das comunicações com HTTPS.

#### **8.2. M2.1 — Documentação de Vulnerabilidades**
* **Objetivo:** Verificar o processo de documentação e correção de vulnerabilidades (para Q2/H2.x).
* **Passos de Execução:**
    1.  Executar uma ferramenta de análise estática (SAST), como o Snyk, nos repositórios GitHub (`guardioes-api` e `guardioes-app`) (para H2.2).
    2.  Registrar o número de vulnerabilidades Críticas e Altas.
    3.  Acessar o repositório do projeto e filtrar PRs/issues com label "fix" ou "security" (para H2.1/H2.3).
    4.  Documentar a quantidade encontrada.
* **Evidência:** Relatório da ferramenta SAST, Screenshots do GitHub (issues/PRs).
* **Cálculo:** `Nº de pull requests ou issues com label "fix"` e Contagem de vulnerabilidades (Crítica/Alta).
* **Critério (Valor-alvo):** (Valor `???`) Será: 0 Vulnerabilidades Críticas.

#### **8.3. M3.1 — Armazenamento Local Seguro**
* **Objetivo:** Medir o percentual de dados sensíveis criptografados localmente (para Q3/H3.x).
* **Passos de Execução:**
    1.  Mapear todas as variáveis sensíveis armazenadas localmente (ex: token, dados de usuário).
    2.  Instalar o app no emulador/dispositivo (com `adb`).
    3.  Fazer login e usar o app.
    4.  Usar `adb shell` para navegar e inspecionar os arquivos de dados do app (ex: `shared_prefs`, `databases`).
    5.  Verificar (por análise de código ou inspeção) se os dados mapeados estão em texto claro.
* **Evidência:** Screenshots dos arquivos de dados (`adb shell`), trechos da análise de código.
* **Cálculo:** `(Nº de variáveis sensíveis criptografadas / Nº total de variáveis sensíveis) × 100`.
* **Critério (Valor-alvo):** ≥ 100%.

#### **8.4. M3.2 — Tempo de Descriptografia** (é necessário revisao por conta da falta de dados relacionados)
* **Objetivo:** Medir o tempo médio de descriptografia de dados locais (para Q3).
* **Passos de Execução:**
    1.  Usar o Android Studio Profiler (CPU Profiler).
    2.  Executar a ação que lê dados criptografados (ex: abrir o app, acessar perfil).
    3.  Identificar e medir o tempo (latência) da função de descriptografia (coletar 10 amostras).
    4.  Calcular a média dos tempos obtidos.
* **Evidência:** Logs do profiler com os tempos das funções.
* **Cálculo:** Média dos tempos de descriptografia.
* **Critério (Valor-alvo):** ≤ 1s.

#### **8.5. M4.1 — Alertas de Integridade** (é necessário revisao por conta da falta de dados relacionados a criptografia)
* **Objetivo:** Garantir identificação de modificações não autorizadas (para Q4/H4.x).
* **Passos de Execução:**
    1.  Interceptar uma requisição válida (ex: Reporte de Sintoma) usando o Burp Suite.
    2.  Modificar os dados da requisição (ex: alterar o ID do usuário, o sintoma ou o timestamp).
    3.  Enviar a requisição modificada para a API.
    4.  Verificar se a API rejeita a requisição (erro 4xx) ou se ela é aceita (falha de integridade).
* **Evidência:** Logs do Burp Suite (requisição original, modificada e resposta da API).
* **Cálculo:** (Fórmula `???`) Será: Descritivo (Sim/Não) se o mecanismo de verificação (hash/checksum) existe e funciona.
* **Critério (Valor-alvo):** (Valor `???`) Será: Rejeição de 100% das modificações não autorizadas.

#### **8.6. M5.1 — Rastreabilidade de Operações**
* **Objetivo:** Assegurar rastreabilidade de operações críticas (para Q5/H5.x).
* **Passos de Execução:**
    1.  Identificar operações críticas no sistema (ex: Login, Reporte de sintoma, Alteração de cadastro).
    2.  Executar cada operação no app.
    3.  Verificar os logs do backend (API).
    4.  Confirmar que a operação foi registrada com dados suficientes (ex: UserID, Ação, Timestamp, IP de origem) para garantir a cobertura.
* **Evidência:** Amostras dos logs da API (backend).
* **Cálculo:** (Fórmula `???`) Será: `(Nº de operações críticas com log adequado / Total de operações críticas testadas) × 100`.
* **Critério (Valor-alvo):** (Valor `???`) Será: 100% de cobertura de logs para operações críticas.

---

### **9. Cronograma de Execução (Planejado)**

Este cronograma define o tempo planejado para a execução da Fase 4.

| Fase | Atividade | Duração Estimada | Responsáveis (Planejados) |
| :--- | :--- | :--- | :--- |
| **Preparação** | Configuração de ambientes, ferramentas, templates | 2 dias | Equipe completa |
| **Execução (Fase 4)** | Execução dos CTs de Adequação Funcional (M1.1 a M2.2) | 3 dias | Avaliadores 1, 2 |
| **Execução (Fase 4)** | Execução dos CTs de Segurança (M1.1 a M5.1) | 4 dias | Avaliadores 3, 4 |
| **Consolidação** | Análise de dados e redação do relatório final | 2 dias | Equipe completa |

### **10. Riscos e Mitigações**

| Risco | Probabilidade | Impacto | Mitigação |
| :--- | :--- | :--- | :--- |
| **API de backend instável** | Alta | Alto | Utilizar uma instância Docker local e estável da API (`guardioes-api`) para isolar os testes. |
| **Ambiente inconsistente** | Média | Alto | Padronização de 1 emulador (Pixel 6, API 33) e 1 dispositivo físico para todos os testes. |
| **Falha na reprodução de bugs** | Média | Alto | Captura sistemática de evidências (logs `adb`, vídeos de tela, logs do proxy) e steps-to-reproduce detalhados. |
| **Limitações na análise de seg.** | Alta | Médio | Focar em testes de caixa-cinza (proxy) e SAST (código), reconhecendo a ausência de um pentest completo e declarando isso no relatório final. |

---

### **11. Consolidação, Análise e Julgamento (Pós-Fase 4)**

#### **11.1. Processo de Consolidação**
* Agregação de todas as planilhas de resultados da Fase 4.
* Cálculo automático das fórmulas de métricas (Fase 2) usando os dados coletados.
* Classificação final por métrica usando os Níveis de Pontuação.

#### **11.2. Análise de Resultados**
* Registro de problemas críticos e identificação de padrões de falhas.
* Análise de correlação (ex: Métrica AF-M2.1 vs. AF-M2.2).

#### **11.3. Relatório Final**
* O relatório final conterá o objetivo, método, tabelas de métricas, gráficos de conformidade e anexos com evidências.

#### **11.4. Níveis de Pontuação e Julgamento Global**
O julgamento dos resultados da Fase 4 seguirá os critérios definidos no documento `pontuacao.md`.

### **12. Critérios de Aceitação do Relatório Final**

* **Rastreabilidade completa:** Todas as métricas devem possuir evidência anexada, rastreável ao seu Caso de Teste (Fase 4).
* **Consistência metodológica:** Todas as métricas devem ser calculadas conforme definido na Fase 2.
* **Clareza nos resultados:** Cada métrica deve ter um julgamento final (Atende / Parcial / Não atende) baseado nos critérios.
* **Transparência:** Limitações da avaliação (riscos que ocorreram) devem ser declaradas.

### **13. Conclusão do Método de Avaliação**

Este plano (Fase 3) garante que a Fase 4 seja executada de forma que atenda aos requisitos da disciplina:

* Explica como avaliar (procedimentos por métrica).
* Define o que registrar (evidências).
* Determina recursos necessários (ambiente e ferramentas).
* Apresenta cronograma e riscos.

### 14. Cronograma de Planejamento da equipe

| Métrica (ID) | Teste de Avaliação | Responsável(is) |
|---|---|---|
| Adequação Funcional |  |  |
| AF-M1.1 | Taxa de Sucesso no Cadastro Completo | Fernanda Vaz  |
| AF-M1.2 | Tempo de Recuperação de Senha | Fernanda Vaz |
| AF-M2.1 | Taxa de Sucesso de Operações Principais | João Pedro Costa |
| AF-M2.2 | Taxa de Perda de Registros de Saúde |Vinícius Rufino  |
| Segurança |  |  |
| SEG-M1.1 | Utilização de HTTPS (Análise de Tráfego) | Oscar de Brito |
| SEG-M2.1 | Documentação de Vulnerabilidades (Análise SAST) | Yan Werlley |
| SEG-M3.1 | Armazenamento Local Seguro (Análise adb) | Marcella Anderle |
| SEG-M3.2 | Tempo de Descriptografia (Profiling) | Marcella Anderle |
| SEG-M4.1 | Alertas de Integridade (Manipulação de Requisição) | Oscar de Brito |
| SEG-M5.1 | Rastreabilidade de Operações (Análise de Logs) | Vinícius Rufino |


## Declaração de Uso de IA
Este documento foi estruturado e consolidado com o auxílio de uma ferramenta de Inteligência Artificial (Gemini) para garantir a consistência, a rastreabilidade entre as Fases 1 e 2, e a aderência à metodologia GQM, sob a supervisão e revisão da equipe do projeto.

## Histórico de Versões

| Versão | Data | Descrição | Autor | Revisor |
|:------:|:----------|:-------------------------------------------------------|:----------------------------------------------------------------------|:-------:|
| 1.0 | 12/10/2025 | Criação do documento inicial e adição do conteúdo | [João Pedro Costa](https://github.com/johnaopedro) | — |
