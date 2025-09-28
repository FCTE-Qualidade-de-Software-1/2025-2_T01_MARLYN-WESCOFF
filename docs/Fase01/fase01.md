# **Guardiões - Propósito da Avaliação**

## Introdução

Nesta fase inicial, buscamos definir os fundamentos da avaliação de qualidade do software **Guardiões da Saúde (App + API)**. O principal objetivo é compreender o propósito da avaliação, identificar os produtos a serem avaliados e selecionar o modelo de qualidade mais adequado.

O propósito da avaliação é verificar a efetividade do Guardiões da Saúde como ferramenta de vigilância epidemiológica participativa, capaz de transformar relatos da população em informações estratégicas para a saúde pública. A avaliação destina-se a diferentes públicos: a sociedade em geral, que acessa boletins epidemiológicos; a comunidade acadêmica (UnB e parceiros), que utiliza os dados para monitoramento e pesquisa; e os gestores de saúde do SUS, que empregam os resultados para decisões específicas, como acionar planos de contingência ou intensificar ações preventivas em áreas críticas.

Optamos pelo método **GQM (Goal-Question-Metric)**, com foco em definir metas claras para avaliar a Adequação Funcional e a **Segurança**, características essenciais no contexto de vigilância epidemiológica e de proteção de dados sensíveis. Essa etapa estabelece as bases conceituais e práticas que nortearão as fases futuras, em conformidade com a norma **ISO/IEC 25000 (SQuaRE).**

## Sobre o Projeto

- **Nome:** Guardiões da Saúde (Aplicativo e API)  
- **Descrição:** Plataforma de saúde participativa para coleta, monitoramento e análise de dados em saúde, apoiando a vigilância epidemiológica comunitária.  
- **Instituição:** UnB - Universidade de Brasília 
- **Repositórios:**  
  - [Guardiões App (Frontend)](https://github.com/ProEpiDesenvolvimento/guardioes-app)  
  - [Guardiões API (Backend)](https://github.com/ProEpiDesenvolvimento/guardioes-api)  
- **Página oficial (Play Store):** [Guardiões da Saúde](https://play.google.com/store/apps/details?id=com.guardioesapp&hl=pt_BR)  
- **Grupo:** ProEpi Desenvolvimento  

De acordo com o modelo [ISO/IEC 25010:2023](https://cdn.standards.iteh.ai/samples/35733/2ca18b477b7845a5b8cae39d6de0c098/ISO-IEC-25010-2011.pdf), a avaliação se concentrará em:

- **Adequação Funcional**  
  Capacidade do software de fornecer funções que atendam às necessidades explícitas e implícitas dos usuários.  
  Subcaracterísticas:  
    - Completude: todas as funções necessárias estão presentes.  
    - Corretude: funções fornecem resultados corretos.  
    - Adequação: funções atendem exatamente ao propósito pretendido.

- **Segurança**  
  Capacidade do software de proteger informações e dados, prevenindo acessos não autorizados, uso indevido e danos.  
  Subcaracterísticas:  
    - Confidencialidade: proteção contra acesso não autorizado.  
    - Integridade: prevenção de modificações não autorizadas.  
    - Não-repúdio: garantia de que ações ou transações não podem ser negadas.  
    - Responsividade à Autenticação: autenticação adequada para acesso seguro.  
    - Proteção contra falhas: resiliência contra ataques e falhas de segurança.



## Requisitante e Partes Interessadas

O **requisitante principal** da avaliação é a **ProEpi**, em parceria com a **Sala de Situação em Saúde da UnB (FS/UnB)**, responsáveis pela concepção, manutenção e direcionamento estratégico do Guardiões da Saúde.

## Perfis de Usuário e Stakeholders

- **Cidadão (usuário final):**  
  Fornecedor de dados de saúde por meio do registro diário de sintomas.  
  Necessidades: interface simples, rapidez no preenchimento e garantia de privacidade.  
  Influência: a usabilidade do sistema e a proteção de dados se tornam critérios de avaliação.

- **Gestor de Saúde Pública (stakeholder institucional):**  
  Profissional de secretarias de saúde ou do Ministério da Saúde.  
  Necessidades: dados agregados e anonimizados para monitorar surtos e planejar ações.  
  Influência: direciona a avaliação para a adequação funcional e para a confiabilidade das informações.

- **Pesquisador/Epidemiologista (stakeholder acadêmico):**  
  Utiliza a base de dados para estudos científicos e validação de modelos epidemiológicos.  
  Necessidades: dados confiáveis, anonimizados e bem estruturados.  
  Influência: orienta a avaliação em critérios de qualidade de dados e interoperabilidade.

- **Administrador do Sistema (equipe técnica):**  
  Responsável por manter a infraestrutura do app e da API.  
  Necessidades: estabilidade, segurança da informação e monitoramento contínuo.  
  Influência: foca a avaliação em desempenho, manutenibilidade e segurança.

## Critérios de Avaliação

| **Critério** | **Descrição** |
|:----------------|:----------------|
| xxxxx | xxxxx |
| xxxxx | xxxxx |
| xxxxx | xxxxx |
| xxxxx | xxxxx |
| xxxxx | xxxxx |

---

## Contribuição aos Objetivos de Desenvolvimento Sustentável (ODS)
## ODS 3 – Saúde e Bem-Estar
- Promove prevenção e monitoramento de doenças.  
- Ajuda no fortalecimento da vigilância epidemiológica.  
- Contribui para responder rapidamente a surtos e emergências de saúde.  

## ODS 9 – Indústria, Inovação e Infraestrutura
- Uso de tecnologia móvel para inovação em saúde pública.  
- Mostra como infraestruturas digitais podem apoiar serviços essenciais.  

## ODS 11 – Cidades e Comunidades Sustentáveis
- Auxilia cidades a monitorarem a saúde da população em larga escala.  
- Permite planejamento urbano e sanitário mais efetivo.  

## ODS 16 – Paz, Justiça e Instituições Eficazes
- Reforça a transparência e confiança entre governo e sociedade.  
- Incentiva participação cidadã na gestão da saúde pública.  

## ODS 17 – Parcerias e Meios de Implementação
- Viabiliza colaboração entre governo, universidades, empresas e sociedade civil no uso dos dados coletados.

## Partes Interessadas  

## Classificação do Tipo de Produto  

O Guardiões da Saúde é classificado como um Sistema de Informação em Saúde (SIS) com foco em Vigilância Epidemiológica Participativa e Ciência Cidadã.

Arquiteturalmente, é uma aplicação **mobile cliente-servidor**, composta por um frontend e um backend.

## Critérios de Priorização das Características

As características de qualidade Adequação Funcional e Segurança foram priorizadas com base nos seguintes critérios:

-
-
-

## Escopo, Profundidade e Objetos de Avaliação  

- Escopo:
- Profundidade:
- Objetos de avaliação:


---

## Tabela de Contribuição
| Identificação   | Nome completo     | Contribuição (%) |
|-----------------|-----------------|-----------------|
| 190030801       | João Pedro Costa | xxx             |
| 221004415       | Fernanda Vaz     | xxx             |
| 211031790       | Oscar de Brito     | xxx             |

## Histórico de Versões

| Versão | Data       | Descrição                                                   | Autor | Revisor |
|:------:|:----------|:------------------------------------------------------------|:-----|:-------:|
| `1.0`  | 26/09/2025 | Criação do Documento inicial                                | [João Pedro Costa](https://github.com/johnaopedro) | — |
| `1.1`  | 28/09/2025 | Ajustando estrutura do documento para que se adeque ao que é pedido na documentação do trabalho | [João Pedro Costa](https://github.com/johnaopedro) | — |
| `1.2`  | 28/09/2025 | Atualização do documento                                     | [Fernanda Vaz](https://github.com/Fernandavazgit1) | [Fernanda Vaz](https://github.com/Fernandavazgit1) |
| `1.3`  | 28/09/2025 | Adição do conteudo sobre classificação do tipo de produto e perfis de usuário | [João Pedro Costa](https://github.com/johnaopedro) | — |
