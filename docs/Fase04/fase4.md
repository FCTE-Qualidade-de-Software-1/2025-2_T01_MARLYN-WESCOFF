# Resultados da Avaliação: Adequação Funcional.

Esta fase detalha a execução do plano de avaliação do **Guardiões da Saúde**, respondendo às perguntas, comparando com as hipóteses levantadas e rastreando o plano de qualidade definido na fase 2 e 3.

## Adequação Funcional: Respostas e Hipóteses

| Característica | Hipótese (H) | Justificativa Chave |
| :--- | :--- | :--- |
| **Completude Funcional** | **H1.1:** O sistema permite criar contas com todos os campos obrigatórios (nome, instituição, matrícula, e-mail e senha). | *[Exemplo: O cadastro foi concluído com sucesso em 100% das 10 tentativas realizadas no ambiente de teste.]* |
| **Completude Funcional** | **H1.2:** O sistema permite recuperar senha e atualizar dados cadastrais. | As funcionalidades de atualização cadastral (Nome/Gênero) e validação de senha funcionaram perfeitamente nos testes T1.3, T2.5 e T3.1. O fluxo de recuperação de senha ainda aguarda medição de tempo. |
| **Corretude Funcional** | **H2.1:** As funções básicas do aplicativo funcionam sem interrupção ou falha. | **Parcialmente Atingida.** As funções administrativas (Diário, Perfil, Vacinação) operam sem falhas (15/18 sucessos), mas a funcionalidade de **Mapa/Geolocalização falhou em 100% dos testes** devido a erro de permissão não tratado no ambiente. |
| **Corretude Funcional** | **H2.2:** Os dados de saúde (sintomas e localização) são processados sem perda ou duplicação. | Os testes T3.4 e T2.3 confirmaram que o sistema evita duplicidade e registra corretamente os dados no calendário. A validação quantitativa (envios vs. banco) ainda será documentada. |

## Segurança: Respostas e Hipóteses

| Característica | Hipótese (H) | Justificativa Chave |
| :--- | :--- | :--- |
| **Confidencialidade** | **H1.1:** O sistema utiliza criptografia para comunicações entre cliente e servidor (HTTPS/TLS). | *[Preencher com análise do Burp Suite. Todas as requisições foram HTTPS?]* |
| **Confidencialidade** | **H2.1 / H2.3:** O código é revisado e utiliza ferramentas automatizadas (SAST) para identificar vulnerabilidades. | *[Preencher com relatório do Snyk. Quantas vulnerabilidades críticas foram achadas?]* |
| **Confidencialidade** | **H3.1:** Nenhum dado pessoal é armazenado em texto claro localmente. | *[Preencher com análise do `adb shell`. O token ou senha estava visível no SharedPreferences?]* |
| **Confidencialidade** | **H3.2:** O tempo de descriptografia de dados locais não impacta a usabilidade. | *[Preencher com dados do Profiler. A média foi ≤ 1s?]* |
| **Integridade** | **H4.1:** Mecanismos de validação detectam alterações não autorizadas nos dados em trânsito. | *[Preencher com teste de manipulação. A API rejeitou os dados alterados?]* |
| **Integridade** | **H5.1:** Operações críticas são registradas em logs de auditoria para garantir rastreabilidade. | *[Preencher com análise de logs. O login e reporte geraram logs completos?]* |

## Níveis de pontuação

Os níveis abaixo foram preenchidos conforme a classificação obtida após o cálculo das fórmulas definidas na Fase 2 e a execução dos testes.

| **MÉTRICA** | **RESULTADO** | **CLASSIFICAÇÃO** |
| ----------- | ------------- | ----------------- |
| **ADEQUAÇÃO FUNCIONAL** | | |
| M1.1 (Cadastro) | **90%** | **Excelente** |
| M1.2 (Recuperação Senha) | **1,33 min** | **Excelente** |
| M2.1 (Operações Principais) | **87,5%** | **Bom** |
| M2.2 (Perda de Dados) | *[Pendente]* | *-* |
| **SEGURANÇA** | | |
| M1.1 (HTTPS) | **100%** | **Excelente** |
| M2.1 (Vulnerabilidades) | *[Pendente]* | *-* |
| M3.1 (Armazenamento Local) | *[Pendente]* | *-* |
| M3.2 (Tempo Descriptografia) | *[Pendente]* | *-* |
| M4.1 (Integridade) | **100% (Rejeição)** | **Excelente** |
| M5.1 (Rastreabilidade) | *[Pendente]* | *-* |

## Critérios de julgamento

Os critérios globais seguem as definições estabelecidas no documento de pontuação.

### Adequação Funcional

- **Aceitável**: > 70% das métricas classificadas como *Bom* ou *Excelente*. Indica que as funcionalidades satisfazem os requisitos com qualidade.
- **Parcialmente Aceitável**: <= 35% das métricas em nível *Insuficiente*. O sistema atende em parte, mas com falhas perceptíveis.
- **Inaceitável**: > 35% das métricas em nível *Insuficiente*. As falhas comprometem a funcionalidade esperada.

> Resultado: **Aceitável.**
> Com 100% das métricas avaliadas até agora (M1.1, M1.2 e M2.1) atingindo os níveis "Bom" ou "Excelente", a característica já satisfaz o critério de aceitação, indicando que as funcionalidades atendem aos requisitos com qualidade adequada.

### Segurança

- **Aceitável**: > 70% das métricas classificadas como *Bom* ou *Excelente*. O sistema segue boas práticas e tem defesa adequada.
- **Parcialmente Aceitável**: < 35% das métricas atingindo *Insuficiente*. Há vulnerabilidades de risco baixo/médio.
- **Inaceitável**: >= 35% das métricas atingindo *Insuficiente*. Falhas críticas comprometem integridade ou confidencialidade.

> Resultado: **[Inserir Resultado Final: Ex: Parcialmente Aceitável. Requer correção no armazenamento local.]**

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