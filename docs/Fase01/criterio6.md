# Escopo, profundidade e objetos de avaliação

## **Escopo** 
A avaliação focará nas características essenciais de **Adequação Funcional** e **Segurança**. O objetivo é garantir que o aplicativo cumpra suas funções declaradas e proteja os dados dos usuários, deixando as demais características do modelo [ISO/IEC 25010](#ref1) fora desta análise.

## **Profundidade**
A análise será conduzida em nível de subcaracterísticas, focando em Adequação Funcional e Segurança, com base em evidências públicas como a descrição na loja de aplicativos, documentação oficial do [Guardiões da Saúde](https://proepidesenvolvimento.github.io/guardioes-api/#beneficios) e o código-fonte no GitHub.


## Seleção Final

Diante do processo de priorização realizada na etapa [1.5- Seleção e Priorização de Características](criterio5.md), apenas quatro subcaracterísticas serão efetivamente analisadas neste trabalho:

**Adequação Funcional:**  
  - Completude Funcional  
  - Corretude Funcional  

**Segurança:**  
  - Confidencialidade  
  - Integridade  

---

### Justificativa da Seleção

A seleção das subcaracterísticas considerou três critérios principais — **risco, impacto e esforço** — sempre em relação aos stakeholders e ao propósito do sistema Guardiões da Saúde, voltado à vigilância epidemiológica participativa.

- **Completude Funcional:** escolhida por representar risco alto caso ausente, pois a falta de funções necessárias comprometeria a coleta de dados da população. O impacto é direto para **cidadãos** (registro de sintomas) e **gestores de saúde** (dados insuficientes para decisão). O esforço de análise é viável, dado que pode ser conduzido com checklist de requisitos.  

- **Corretude Funcional:** selecionada por impacto crítico na confiabilidade dos resultados. Dados incorretos inviabilizam análises epidemiológicas e decisões do **SUS**, além de comprometer a credibilidade científica junto a **pesquisadores**. O risco de dano social e reputacional é elevado.  

- **Confidencialidade:** priorizada por ser requisito legal (LGPD) e pelo risco altíssimo de vazamento de dados sensíveis de saúde. O impacto negativo recai sobre **cidadãos** e sobre a confiança pública no sistema.  

- **Integridade:** escolhida por assegurar que os dados não sejam alterados indevidamente. O risco é alto, pois modificações não autorizadas podem distorcer mapas epidemiológicos e induzir gestores a erros estratégicos.  


### Justificativa da Exclusão

As demais subcaracterísticas foram excluídas após análise de risco, impacto e esforço, sendo classificadas como de menor prioridade para o escopo deste trabalho acadêmico:

- **Adequação Funcional – Adequação:** embora importante, foi considerada de impacto moderado em comparação com completude e corretude. Exige avaliação qualitativa mais extensa (usabilidade, eficiência de tarefas), que não é viável no tempo disponível.  

- **Segurança - Autenticidade:** o Guardiões da Saúde é um sistema voluntário e aberto à população, exigir autenticação forte (Autenticidade) não é tão central quanto, por exemplo, Confidencialidade e Integridade. na prática, o risco maior está em proteger dados sensíveis e garantir que eles não sejam alterados indevidamente, mais do que em validar rigidamente quem reporta.  

- **Segurança – Não-repúdio:** relevante para auditoria e processos jurídicos, mas de risco menor neste estágio, pois os dados já são anonimizados e a necessidade de prova legal não é imediata.  

- **Segurança – Responsabilidade:** fundamental em ambientes corporativos, mas o esforço de implementação e análise (auditoria completa, logs detalhados) é elevado, não sendo proporcional ao escopo acadêmico deste estudo.  

- **Proteção contra falhas (Segurança/Confiabilidade):** foi despriorizada pelo esforço analítico (exige testes de carga, falhas simuladas) e por não se configurar como requisito imediato para os stakeholders primários deste trabalho.  

### Conclusão

Assim, a priorização concentrou-se em **subcaracterísticas de confiança, legalidade e efetividade do Guardiões da Saúde**, equilibrando **risco elevado**, **alto impacto para stakeholders-chave** (cidadãos, gestores do SUS, pesquisadores, administradores) e **viabilidade analítica dentro do prazo do trabalho acadêmico**.

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
|  1.0  | 28/09/2025 | Criação do Documento inicial      | [Oscar de Brito](https://github.com/OscarDeBrito) | — |
|  1.1  | 30/09/2025 | Adição do conteúdo do critério 6 e referêcias | [João Pedro Costa](https://github.com/johnaopedro) | — |
| 1.2    | 30/09/2025 | seleção final / Justificativa de seleção e exclusão | [Oscar de Brito](https://github.com/OscarDeBrito)/[Marcella Anderle](https://github.com/marcellaanderle) | — |

