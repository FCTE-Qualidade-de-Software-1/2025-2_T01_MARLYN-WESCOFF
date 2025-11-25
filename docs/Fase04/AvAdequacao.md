# Resultados da Avaliação - Adequação Funcional

## 1. Introdução
Esta seção detalha os resultados obtidos durante a execução dos testes funcionais no aplicativo **Guardiões da Saúde**. A avaliação seguiu o planejamento definido na Fase 3, cobrindo as subcaracterísticas de Completude e Corretude Funcional.

## 2. Ambiente de Execução
Os testes foram realizados conforme as especificações abaixo, garantindo a reprodutibilidade dos cenários:

| Item | Detalhe |
| :--- | :--- |
| **Versão do Software** | Guardiões da Saúde (Build de Teste gerada via Android Studio / APK) |
| **Dispositivos** | Emulador Android |
| **Sistema Operacional** | Android 11 |
| **Ferramentas de Apoio** | Gravador de Tela nativo |

---

## 3. Completude Funcional (Q1)

### 3.1. Métrica AF-M1.1: Taxa de Sucesso no Cadastro Completo
**Objetivo:** Verificar se o sistema permite criar contas com todos os campos obrigatórios preenchidos (H1.1).

| ID Teste | Cenário | Resultado (Sucesso/Falha) | Link da Evidência (Vídeo/Print) |
|---------|---------|---------------------------|---------------------------------|
| T-CAD-01 | Cadastro com dados válidos (Usuário 1) | Sucesso | [link](https://youtube.com/shorts/u8YjErM28zI?feature=share) |
| T-CAD-02 | Cadastro com dados válidos (Usuário 2) | Sucesso | [link](https://youtube.com/shorts/Rd77DBF-f-w?feature=share) |
| T-CAD-03 | Cadastro com dados válidos (Usuário 3) | Sucesso | [link](https://youtube.com/shorts/PEt-PELYOQw?feature=share) |
| T-CAD-04 | Cadastro com dados válidos (Usuário 4) | Sucesso | [link](https://youtube.com/shorts/v1ptqXH5sYs?feature=share) |
| T-CAD-05 | Cadastro com dados válidos (Usuário 5) | Sucesso | [link](https://youtube.com/shorts/QrU1pQVETS0?feature=share) |
| T-CAD-06 | Cadastro com dados válidos (Usuário 6) | Sucesso | [link](https://youtube.com/shorts/4wMvA2h33bo?feature=share) |
| T-CAD-07 | Cadastro com dados válidos (Usuário 7) | Sucesso | [link](https://youtube.com/shorts/w8uLkUepMWo?feature=share) |
| T-CAD-08 | Cadastro com dados válidos (Usuário 8) | **Falha** | [link](https://youtube.com/shorts/p3wcxJ4_jrM?feature=share) |
| T-CAD-09 | Cadastro com dados válidos (Usuário 9) | Sucesso | [link](https://youtube.com/shorts/bGYpSa3J20Y?feature=share) |
| T-CAD-10 | Cadastro com dados válidos (Usuário 10) | Sucesso | [link](https://youtube.com/shorts/Yg7Xo7sbdn4?feature=share) |

* **Cálculo:** `(Sucessos / 10) * 100` = **90%**
* (9 / 10) * 100 = 90% *
* **Critério (Alvo):** ≥ 95%
* **Status:** *Não Atingido*



---

### 3.2. Métrica AF-M1.2: Tempo de Recuperação de Senha
**Objetivo:** Medir o tempo entre a solicitação e a conclusão da recuperação de senha (H1.2).

| ID Teste | Hora Início | Hora Conclusão | Tempo Total (min) | Link da Evidência |
| :--- | :--- | :--- | :--- | :--- |
| T-REC-01 | 00:00 | 00:00 | 0 min | [Link Aqui] |
| T-REC-02 | 00:00 | 00:00 | 0 min | [Link Aqui] |
| T-REC-03 | 00:00 | 00:00 | 0 min | [Link Aqui] |

* **Média:** **[X] minutos**
* **Critério (Alvo):** ≤ 5 minutos
* **Status:** *[Atingido / Não Atingido]*

---

## 4. Corretude Funcional (Q2)

### 4.1. Métrica AF-M2.1: Taxa de Sucesso de Operações Principais
**Objetivo:** Avaliar a execução sem falhas críticas das funções essenciais (H2.1).

**Resumo da Execução:**
* **Data:** 24/11/2025
* **Total de Testes:** 18
* **Sucessos:** 15
* **Falhas:** 3

#### Tabela de Resultados e Evidências

| ID Teste | Funcionalidade | Resultado | Observação / Erro | Link do Vídeo (Evidência) |
| :--- | :--- | :--- | :--- | :--- |
| **TESTE 1** | **(Bateria 1)** | | | [Teste 1](../videos/Taxa_de_Sucesso_de_Operações_Principais_Teste1.mp4) |
| T1.1 | Diário de Saúde | **Sucesso** | Calendário registrou corretamente. | |
| T1.2 | Mapa | **Falha** | Erro de permissão/Ambiente. | |
| T1.3 | Perfil | **Sucesso** | Gênero alterado. | |
| T1.4 | Segurança | **Sucesso** | Troca de senha OK. | |
| T1.5 | Vacinação | **Sucesso** | Dose adicionada. | |
| T1.6 | Navegação | **Sucesso** | Links externos OK. | |
| **TESTE 2** | **(Bateria 2)** | | | [Teste 2](../videos/Taxa_de_Sucesso_de_Operações_Principais_Teste2.mp4)  |
| T2.1 | Navegação | **Sucesso** | Acesso normal. | |
| T2.2 | Mapa | **Falha** | Erro de permissão. | |
| T2.3 | Diário de Saúde | **Sucesso** | Validação de registro OK. | |
| T2.4 | Segurança | **Sucesso** | Validação de senha OK. | |
| T2.5 | Perfil | **Sucesso** | Nome alterado. | |
| T2.6 | Login | **Sucesso** | Login válido. | |
| **TESTE 3** | **(Bateria 3)** | | | [Teste 3](../videos/Taxa_de_Sucesso_de_Operações_Principais_Teste3.mp4)  |
| T3.1 | Perfil | **Sucesso** | Múltiplas alterações. | |
| T3.2 | Segurança | **Sucesso** | Tratou senha inválida corretamente. | |
| T3.3 | Vacinação | **Sucesso** | Data antiga aceita. | |
| T3.4 | Diário de Saúde | **Sucesso** | Duplicidade tratada. | |
| T3.5 | Mapa | **Falha** | Erro de permissão. | |
| T3.6 | Navegação | **Sucesso** | Redirecionamento OK. | |

* **Cálculo:** `(15 / 18) * 100` = **83,33%**
* **Critério (Alvo):** ≥ 98%
* **Status:** <span style="color:red">**Não Atingido**</span>

#### Nota sobre a Falha de Localização (Mapa)
Durante os testes T1.2, T2.2 e T3.5, a localização do dispositivo (emulador) estava desligada. O aplicativo não tratou essa condição adequadamente (solicitando ativação ou mostrando mensagem de erro amigável), resultando na falha da operação de visualização do mapa. Além disso, notou-se uma insistência excessiva na solicitação de permissão de localização em telas que não dependem desse recurso, indicando um problema de usabilidade e implementação de permissões.

---

### 4.2. Métrica AF-M2.2: Taxa de Perda de Registros de Saúde
**Objetivo:** Verificar se dados enviados pelo app são gravados no banco sem perdas (H2.2).

| Qtd. Envios (App) | Qtd. Registros (Banco de Dados) | Diferença | Link da Evidência (Logs/Query) |
| :---: | :---: | :---: | :--- |
| 50 | *[Preencher]* | *[Preencher]* | [Link Aqui] |

* **Cálculo:** `(Perdidos / Enviados) * 100` = **[X]%**
* **Critério (Alvo):** 0%
* **Status:** *[Atingido / Não Atingido]*

---

## 5. Análise Global e Julgamento

A classificação abaixo segue rigorosamente os Níveis de Pontuação definidos na Fase 2.

### 5.1. Classificação das Métricas

| ID | Métrica | Valor Obtido | Nota Equiv. (0-10) | Nível (Classificação) | Justificativa com base no Critério |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **AF-M2.1** | Taxa de Sucesso de Operações | **83,33%** | **8,3** | **Bom** | Enquadra-se na faixa **7 – 8,9**. Cumpre adequadamente a maior parte das métricas propostas (15/18 sucessos), apresentando pequenas falhas ou melhorias possíveis (falha específica no Mapa). |
| **AF-M1.1** | Cadastro Completo | *[Preencher]* | *[0-10]* | *[Definir]* | *[Consultar tabela de pontuação]* |
| **AF-M1.2** | Recuperação de Senha | *[Preencher]* | *[0-10]* | *[Definir]* | *[Consultar tabela de pontuação]* |
| **AF-M2.2** | Perda de Registros | *[Preencher]* | *[0-10]* | *[Definir]* | *[Consultar tabela de pontuação]* |

### 5.2. Julgamento da Característica: Adequação Funcional

Para determinar o resultado final, aplicam-se os seguintes critérios:

* **Aceitável:** > 70% das métricas classificadas como *Bom* ou *Excelente*.
* **Parcialmente Aceitável:** <= 35% das métricas em nível *Insuficiente*.
* **Inaceitável:** > 35% das métricas em nível *Insuficiente*.

> **Parecer Preliminar:** Considerando que a métrica principal (AF-M2.1) foi classificada como **Bom**, se as demais métricas (Cadastro e Perda de Dados) também obtiverem resultados positivos, a característica Adequação Funcional atingirá o nível **Aceitável**. Caso contrário, se houver falhas críticas nas outras métricas, o resultado poderá cair para **Parcialmente Aceitável**.

## Declaração do uso de Inteligência Artificial

\<p style="text-indent:30px; text-align: justify"\>Durante o desenvolvimento deste relatório, foi utilizada a ferramenta de Inteligência Artificial (Gemini) para a estruturação das tabelas de resultados e consolidação das hipóteses definidas nas fases anteriores. Todas as informações, referências e interpretações técnicas foram validadas e ajustadas manualmente pela equipe após a execução dos testes, garantindo a precisão e a coerência com o contexto real do projeto Guardiões da Saúde.\</p\>

## Referências

> 1.  Equipe Marlyn Wescoff. **Critério 2 — Execução da Avaliação: Adequação Funcional**. Fase 2 do Projeto de Qualidade de Software. Disponível no repositório do projeto.

> 2.  Equipe Marlyn Wescoff. **Critério 3 — Execução da Avaliação: Segurança**. Fase 2 do Projeto de Qualidade de Software. Disponível no repositório do projeto.

> 3.  Equipe Marlyn Wescoff. **Níveis de Pontuação e Critérios de Julgamento**. Fase 2 do Projeto de Qualidade de Software. Disponível no repositório do projeto.

## Histórico de Versão

| Versão | Data       | Descrição                         | Autor                               | Revisor |
|:------:|:----------|:----------------------------------|:-------------------------------------|:-------:|
| 1.0    | 24/11/2025 | Criação do Documento inicial e elaboração do documento e dos testes do Q2 | [João Pedro Costa](https://github.com/johnaopedro) |   —    |
| Versão | Data       | Descrição                         | Autor                               | Revisor |
|:------:|:----------|:----------------------------------|:-------------------------------------|:-------:|
| 1.1    | 25/11/2025 | ELABORAÇÃO DOS TESTE:Taxa de Sucesso no Cadastro Completo E Tempo de Recuperação de Senha | FERNANDA VAZ |   —    |
