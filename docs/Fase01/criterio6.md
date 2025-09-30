# Critério 6 — Escopo, profundidade e objetos de avaliação

## **Escopo** 
A avaliação focará nas características essenciais de **Adequação Funcional** e **Segurança**. O objetivo é garantir que o aplicativo cumpra suas funções declaradas e proteja os dados dos usuários, deixando as demais características do modelo [ISO/IEC 25010](#ref1) fora desta análise.

## **Profundidade** 
A análise será conduzida em nível de subcaracterísticas, focando em Adequação Funcional e Segurança, com base em evidências públicas como a descrição na loja de aplicativos, documentação oficial (quando disponível) e o código-fonte no GitHub.

## **Adequação Funcional**
  - Completude Funcional (Functional completeness): Verificação se o conjunto de funções do aplicativo é suficiente para cumprir seu objetivo de vigilância participativa em saúde.
  - Correção Funcional (Functional correctness): Análise se as funções, como o relato de sintomas e a visualização de dados, fornecem os resultados corretos conforme o esperado.
  - Pertinência Funcional (Adequação funcional): Avaliação de como as funções do aplicativo auxiliam os usuários a atingir os objetivos de monitoramento e informação em saúde.

## **Segurança**
  - Confidencialidade (Confidentiality): Como os dados dos usuários são protegidos contra acesso não autorizado, incluindo a criptografia em trânsito mencionada na Play Store.
  - Integridade (Integrity): Medidas para garantir que os dados de saúde reportados não sejam corrompidos ou alterados indevidamente.
  - Autenticidade (Authenticity): Processos para verificar a identidade dos usuários e garantir a legitimidade do acesso.
  - Não-repúdio (Non-repudiation): Garantia de que uma ação realizada por um usuário não pode ser posteriormente negada por ele.
  - Rastreabilidade (Accountability): Capacidade de rastrear as ações de um usuário de forma única, permitindo que sejam atribuídas a ele.

## **Objetos de avaliação**
- Aplicativo cliente (Google Play Store):
  O programa que os usuários instalam. Será avaliado quanto à **adequação funcional**, ou seja, se as funcionalidades descritas (relato de sintomas, acompanhamento de estado de saúde etc.) estão presentes e cumprem o propósito do aplicativo. Também será avaliado quanto à **segurança**, com foco em como protege os dados do usuário no dispositivo e nas permissões solicitadas.
- Repositórios open source (GitHub - Frontend e Backend):
  O código-fonte público do "Guardiões App" e da "Guardiões API". Serão avaliados para verificar a implementação técnica das funcionalidades e para identificar a implementação de práticas de segurança no código.

## Referências Bibliográficas

> <a id="ref1"></a> ISO/IEC 25010:2011: Systems and software engineering - Systems and software Quality Requirements and Evaluation (SQuaRE). Disponível em: [https://aprender3.unb.br/pluginfile.php/3230266/mod_folder/content/0/25010.pdf?forcedownload=1](https://aprender3.unb.br/pluginfile.php/3230266/mod_folder/content/0/25010.pdf?forcedownload=1). Acesso em: 30 de Set. 2025.


## Histórico de Versões

|  Versão |    Data    | Descrição                         | Autor                                | Revisor |
|:-------:|:----------:|:----------------------------------|:-------------------------------------|:-------:|
|  `1.0`  | 28/09/2025 | Criação do Documento inicial      | [Oscar de Brito](https://github.com/OscarDeBrito) | — |
|  `1.1`  | 30/09/2025 | Adição do conteúdo do critério 6 e referêcias | [João Pedro Costa](https://github.com/johnaopedro) | — |
