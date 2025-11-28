# Resultados da Avaliação: Visão Geral

Esta fase detalha a execução do plano de avaliação do **Guardiões da Saúde**, respondendo às perguntas, comparando com as hipóteses levantadas e rastreando o plano de qualidade definido na fase 2 e 3.

## Adequação Funcional: Respostas e Hipóteses

| Característica | Hipótese (H) | Justificativa Chave |
| :--- | :--- | :--- |
| **Completude Funcional** | **H1.1:** O sistema permite criar contas com todos os campos obrigatórios (nome, instituição, matrícula, e-mail e senha). | **Atingida.** O cadastro foi concluído com sucesso em 90% das tentativas. |
| **Completude Funcional** | **H1.2:** O sistema permite recuperar senha e atualizar dados cadastrais. | **Atingida.** O tempo médio de recuperação foi de 1,33 min. Atualização de dados testada com sucesso em cenários de limites e símbolos. |
| **Corretude Funcional** | **H2.1:** As funções básicas do aplicativo funcionam sem interrupção ou falha. | **Atingida (Excelente).** Todas as funções testáveis no ambiente (Diário, Perfil, Vacinação, Login) operaram sem falhas (26/26 sucessos). *Nota: Geolocalização não avaliada devido a restrições de ambiente.* |
| **Corretude Funcional** | **H2.2:** Os dados de saúde (sintomas e localização) são processados sem perda ou duplicação. | Os testes de robustez confirmaram que o sistema evita duplicidade de cliques e datas inválidas. Validação de volume pendente. |

## Segurança: Respostas e Hipóteses

| Característica | Hipótese (H) | Justificativa Chave |
| :--- | :--- | :--- |
| **Confidencialidade** | **H1.1:** O sistema utiliza criptografia para comunicações entre cliente e servidor (HTTPS/TLS). | **Atingida.** Todos os 22 endpoints testados operam exclusivamente sobre HTTPS com protocolo TLS 1.3 e certificados válidos. Não foram identificadas comunicações em texto claro ou downgrade de protocolo. O critério-alvo (100%) foi plenamente atendido, garantindo proteção contra interceptação, espionagem de tráfego e ataques man-in-the-middle.  |
| **Confidencialidade** | **H2.1 / H2.3:** O código é revisado e utiliza ferramentas automatizadas (SAST) para identificar vulnerabilidades. | *[Preencher com relatório do Snyk. Quantas vulnerabilidades críticas foram achadas?]* |
| **Confidencialidade** | **H3.1:** Nenhum dado pessoal é armazenado em texto claro localmente. | *[Preencher com análise do `adb shell`. O token ou senha estava visível no SharedPreferences?]* |
| **Confidencialidade** | **H3.2:** O tempo de descriptografia de dados locais não impacta a usabilidade. | *[Preencher com dados do Profiler. A média foi ≤ 1s?]* |
| **Integridade** | **H4.1:** Mecanismos de validação detectam alterações não autorizadas nos dados em trânsito. | **Atingida.** A API rejeitou 100% das tentativas de manipulação realizadas nos 8 cenários testados — incluindo alteração de IDs, timestamps, flags administrativas, campos sensíveis e tentativas de escalonamento de privilégio. Em todos os casos, o backend respondeu com códigos HTTP adequados (403, 401, 422), demonstrando validação server-side robusta e prevenção efetiva contra ataques de adulteração de payload e violação de integridade. |
| **Integridade** | **H5.1:** Operações críticas são registradas em logs de auditoria para garantir rastreabilidade. | *[Preencher com análise de logs. O login e reporte geraram logs completos?]* |

## Níveis de pontuação

Os níveis abaixo foram preenchidos conforme a classificação obtida após o cálculo das fórmulas definidas na Fase 2 e a execução dos testes.

| **MÉTRICA** | **RESULTADO** | **CLASSIFICAÇÃO** |
| ----------- | ------------- | ----------------- |
| **ADEQUAÇÃO FUNCIONAL** | | |
| M1.1 (Cadastro) | **90%** | **Excelente** |
| M1.2 (Recuperação Senha) | **1,33 min** | **Excelente** |
| M2.1 (Operações Principais) | **100%*** | **Excelente** |
| M2.2 (Perda de Dados) | *[Pendente]* | *-* |
| **SEGURANÇA** | | |
| M1.1 (HTTPS) | **100%** | **Excelente** |
| M2.1 (Vulnerabilidades) | *[Pendente]* | *-* |
| M3.1 (Armazenamento Local) | *[Pendente]* | *-* |
| M3.2 (Tempo Descriptografia) | *[Pendente]* | *-* |
| M4.1 (Integridade) | **100% (Rejeição)** | **Excelente** |
| M5.1 (Rastreabilidade) | *[Pendente]* | *-* |

*\*Nota: Cálculo de M2.1 excluiu testes de Mapa por limitação técnica do ambiente.*

## Critérios de julgamento

Os critérios globais seguem as definições estabelecidas no documento de pontuação.

### Adequação Funcional

- **Aceitável**: > 70% das métricas classificadas como *Bom* ou *Excelente*. Indica que as funcionalidades satisfazem os requisitos com qualidade.
- **Parcialmente Aceitável**: <= 35% das métricas em nível *Insuficiente*. O sistema atende em parte, mas com falhas perceptíveis.
- **Inaceitável**: > 35% das métricas em nível *Insuficiente*. As falhas comprometem a funcionalidade esperada.

> Resultado: **Aceitável.**
> Com 100% das métricas avaliadas até agora atingindo o nível "Excelente", a característica satisfaz plenamente os requisitos de qualidade.

### Segurança

- **Aceitável**: > 70% das métricas classificadas como *Bom* ou *Excelente*. O sistema segue boas práticas e tem defesa adequada.
- **Parcialmente Aceitável**: < 35% das métricas atingindo *Insuficiente*. Há vulnerabilidades de risco baixo/médio.
- **Inaceitável**: >= 35% das métricas atingindo *Insuficiente*. Falhas críticas comprometem integridade ou confidencialidade.

> Resultado: **Aceitável (Preliminar).**
> As métricas avaliadas (Tráfego Seguro e Integridade de Dados) obtiveram pontuação máxima ("Excelente"). O sistema demonstra robustez na comunicação.

## Declaração do uso de Inteligência Artificial

Durante o desenvolvimento deste relatório, foi utilizada a ferramenta de Inteligência Artificial (Gemini) para a estruturação das tabelas de resultados, consolidação das hipóteses e preenchimento inicial com base nos dados de teste fornecidos. Todas as informações, referências e interpretações técnicas foram validadas e ajustadas manualmente pela equipe após a execução dos testes, garantindo a precisão e a coerência com o contexto real do projeto Guardiões da Saúde.
## Referências

> 1. Equipe Marlyn Wescoff. **Critério 2 — Execução da Avaliação: Adequação Funcional**. Fase 2 do Projeto de Qualidade de Software. Disponível no repositório do projeto.

> 2. Equipe Marlyn Wescoff. **Critério 3 — Execução da Avaliação: Segurança**. Fase 2 do Projeto de Qualidade de Software. Disponível no repositório do projeto.

> 3. Equipe Marlyn Wescoff. **Níveis de Pontuação e Critérios de Julgamento**. Fase 2 do Projeto de Qualidade de Software. Disponível no repositório do projeto.

## Histórico de Versão

| Versão | Data | Descrição | Autor | Revisor |
|:------:|:----------|:----------------------------------|:-------------------------------------|:-------:|
| 1.0 | 24/11/2025 | Criação do Documento inicial e artefato da tabela de contribuição | [João Pedro Costa](https://github.com/johnaopedro) | — |
| 1.1 | 24/11/2025 | Atualização dos testes de M1.1 E M4.1 | [Oscar de Brito](https://github.com/OscardeBrito) | — |
| 1.2 | 28/11/2025 | Atualização de M2.1 com exclusão de testes de Mapa | [João Pedro Costa](https://github.com/johnaopedro) | — |