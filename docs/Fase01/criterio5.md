# Critério 5 — Seleção e Priorização de Características

## Critérios de Priorização

Para orientar a seleção das subcaracterísticas de qualidade do software a serem avaliadas, foi adotado o **Método MoSCoW**, um framework de priorização criado nos anos 1990 por **Dai Clegg** no contexto do *Dynamic Systems Development Method (DSDM)*.  

O MoSCoW organiza requisitos ou atributos de qualidade em quatro categorias principais:  

1. **Must have (Obrigatório):** elementos imprescindíveis para o sucesso do projeto. Sua ausência compromete a confiabilidade ou a viabilidade do sistema.  
2. **Should have (Importante):** elementos altamente relevantes, mas que podem ser postergados ou entregues em uma segunda iteração sem inviabilizar a solução.  
3. **Could have (Desejável):** elementos que agregam valor ou benefícios adicionais, mas que não são essenciais; sua implementação depende da disponibilidade de tempo e recursos.  
4. **Won’t have (Não será implementado no momento):** elementos considerados de baixa prioridade e que, de forma deliberada, ficam fora do escopo atual para evitar inchaço de requisitos (*scope creep*).

Essa abordagem garante que a priorização das subcaracterísticas de qualidade seja **transparente, negociada entre stakeholders e alinhada ao contexto do Guardiões da Saúde**.

---

## Priorização das Subcaracterísticas

Com base no modelo **ISO/IEC 25010** e considerando o domínio da **vigilância epidemiológica participativa**, as subcaracterísticas de **Adequação Funcional** e **Segurança** foram classificadas segundo o método MoSCoW.  

Além da categorização, foi atribuída uma **pontuação de peso** para cada categoria:  
- Must = 4  
- Should = 3  
- Could = 2  
- Won’t = 0  

Esse critério permitiu reduzir o conjunto de subcaracterísticas do **ISO/IEC 25010** às que são mais críticas ao contexto do **Guardiões da Saúde**, evitando dispersão analítica e mantendo a consistência metodológica.

---

## Priorização das Subcaracterísticas

**Tabela 1 — Priorização das subcaracterísticas pelo método MoSCoW**

| Subcaracterística | Característica | Categoria MoSCoW | Peso | Decisão Final |
|--------------------|----------------|------------------|------|---------------|
| **Completude Funcional** | Adequação Funcional | Must | 4 | **Será analisada** |
| **Corretude Funcional** | Adequação Funcional | Must | 4 | **Será analisada** |
| **Adequação Funcional** | Adequação Funcional | Should | 3 | Não será analisada |
| **Confidencialidade** | Segurança | Must | 4 | **Será analisada** |
| **Integridade** | Segurança | Must | 4 | **Será analisada** |
| **Autenticidade** | Segurança | Could | 2 | Não será analisada |
| **Não-repúdio** | Segurança | Should | 3 | Não será analisada |
| **Responsabilidade** | Segurança | Could | 2 | Não será analisada |
| **Proteção contra falhas** | Segurança/Confiabilidade | Could | 2 | Não será analisada |

---

**Tabela 2 — Comparação por risco, impacto e esforço de análise**

| Subcaracterística            | Característica        | Risco se ausente | Impacto para stakeholders | Esforço de análise | Decisão Final |
|-------------------------------|-----------------------|------------------|---------------------------|--------------------|---------------|
| **Completude Funcional**      | Adequação Funcional   | Alto             | Alto (cidadãos, gestores, pesquisadores) | Baixo (checklist de requisitos) | **Selecionada** |
| **Corretude Funcional**       | Adequação Funcional   | Alto             | Alto (gestores do SUS, pesquisadores) | Médio (testes funcionais) | **Selecionada** |
| **Adequação Funcional**       | Adequação Funcional   | Médio            | Médio (usuários, usabilidade) | Alto (avaliação qualitativa extensa) | Não selecionada |
| **Confidencialidade**         | Segurança             | Alto             | Alto (cidadãos, LGPD, confiança pública) | Médio (políticas de acesso, criptografia) | **Selecionada** |
| **Integridade**               | Segurança             | Alto             | Alto (gestores, pesquisadores, dados consistentes) | Médio (validação de logs e registros) | **Selecionada** |
| **Autenticidade**             | Segurança             | Baixo/Médio      | Baixo (voluntários; impacto limitado) | Médio (análise de mecanismos de login) | Não selecionada |
| **Não-repúdio**               | Segurança             | Médio            | Médio (auditoria, contexto jurídico futuro) | Alto (exige mecanismos adicionais) | Não selecionada |
| **Responsabilidade**          | Segurança             | Médio            | Médio (auditoria de ações, accountability) | Alto (auditoria completa de logs) | Não selecionada |
| **Proteção contra falhas**    | Segurança / Confiabilidade | Baixo        | Baixo (resiliência técnica, stakeholders indiretos) | Alto (testes de falha e carga) | Não selecionada |

---

## Referências Bibliográficas

1. INTERNATIONAL ORGANIZATION FOR STANDARDIZATION. *ISO/IEC 25010:2011 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — System and software quality models*. Geneva: ISO, 2011. Disponível em: <https://cdn.standards.iteh.ai/samples/35733/2ca18b477b7845a5b8cae39d6de0c098/ISO-IEC-25010-2011.pdf>. Acesso em: 30 set. 2025. 

2. BECKER, Alice.*Método MoSCoW: o que é e como usar na priorização de tarefas*. Voitto, 16 maio 2023. Disponível em: <https://voitto.com.br/blog/artigo/metodo-moscow>. Acesso em: 30 set. 2025.

## Histórico de Versões

| Versão | Data       | Descrição                                         | Autor                                                                 | Revisor |
|:------:|:----------:|:--------------------------------------------------|:----------------------------------------------------------------------|:-------:|
| 1.0    | 28/09/2025 | Criação do documento inicial                      | [Oscar de Brito](https://github.com/OscarDeBrito)                     | —       |
| 1.1    | 30/09/2025 | Inclusão dos critérios de priorização das características | [Marcella Anderle](https://github.com/marcellaanderle)                | —       |
| 1.0    | 30/09/2025 | Aplicação do método MoSCoW para priorização das subcaracterísticas de qualidade | [Oscar de Brito](https://github.com/OscarDeBrito)/[Marcella Anderle](https://github.com/marcellaanderle) | — |

