# Critério 3: Execução da Avaliação - Segurança

## 1. Goal (Objetivo)<a href="#ref1"><sup>1</sup></a>


| Analisar | o aplicativo Guardiões da Saúde |
|----------|--------------------------------|
| Para o propósito de |Avaliar e melhorar |
| Com respeito a | A segurança com foco em confidencialidade e integridade dos dados de saúde do usuário |
| Do ponto de vista da | 	Da equipe de Equipe de desenvolvimento |
| No contexto da |	Disciplina de Qualidade de Software (FCTE - UnB) |

*Tabela 2 — Critério 3: Execução da Avaliação - Segurança*


## 2. Questions (Questões) e 3. Metrics (Métricas)

### Confidencialidade

**Q1:** Os dados de saúde dos usuários estão efetivamente protegidos contra acesso não autorizado, tanto em repouso quanto em trânsito?

**Hipóteses:**

- **1:** O sistema utiliza criptografia para todas as comunicações entre cliente e servidor, protegendo dados em trânsito.

**Q2:** O sistema segue práticas de desenvolvimento seguro e análise de vulnerabilidades?

**Hipóteses:**

  - **1:** O código é periodicamente revisado para identificar vulnerabilidades conhecidas.
  - **2:** O sistema utiliza ferramentas automatizadas de análise de código para detecção de falhas de segurança.
  - **3:** Existe um processo documentado para tratamento e correção de vulnerabilidades identificadas.

**Métricas:**

- **1: Utilização de comunicação utiliza HTTPS**
  - **Objetivo:** Verificar se todas as comunicações entre cliente e servidor utilizam HTTPS/TLS para garantir a proteção dos dados em trânsito.
  - **Método de coleta:** Verificar a configuração do servidor incluindo: Certificados SSL/TLS válidos. Protocolos suportados (ex.: TLS 1.2 ou superior).
  <!--Não foi possível verificar devido ao código do sistema não ter caminhos públicos para conferir se utiliza comunicação HTTPS-->
 

- **2: Documentação para tratamento e correção de vulnerabilidades identificadas**
  - **Objetivo:** Verificar o processo de documentação.
  - **Método de coleta:** Verificar nº de pull requests ou issues com a label fix.

---

### Integridade

**Q1:** Os dados de saúde dos usuários estão efetivamente protegidos contra alteração ou corrupção não autorizada?

**Hipóteses:**

  - **1:** Mecanismos de validação e verificação de integridade detectam alterações não autorizadas.
  - **2:** Qualquer modificação nos dados críticos gera alerta imediato.

**Q2:** Existem mecanismos eficazes para garantir a consistência e rastreabilidade dos dados armazenados no sistema?

**Hipóteses:**

  - **1:** Todas as operações críticas são registradas em logs de auditoria.
  - **2:** O histórico de alterações permite rastrear e restaurar dados, se necessário.

**Métricas:**

- **1: Alertas de Falha na Verificação de Integridade**
  - **Objetivo:** Garantir que qualquer modificação não autorizada em dados críticos de saúde seja identificada e gere um alerta imediato, assegurando a integridade das informações.
  - **Método de coleta:** Verificar a existência de mecanismos de verificação de integridade (ex.: checksums, hash, controle de versão ou trilhas de auditoria).

- **2: Consistência e rastreabilidade dos dados armazenados no sistema**
  - **Objetivo:** Assegurar rastreabilidade das operações críticas.
  - **Método de coleta:** Verificar a existência de operações de log no código em operações críticas.

## 4. Resultados da Coleta <a href="#ref2"><sup>2</sup></a>

### 4.1 Dados Coletados por Métrica


## 5. Análise dos Resultados

### 5.1 Confidencialidade
- **Pontos Fortes:**
- **Pontos de Melhoria:**
  

### 5.2 Integridade
- **Pontos Fortes:**
- **Pontos de Melhoria:**


## 6. Ações de Melhoria

## Diagrama -  Segurança

<div style="width: 640px; height: 480px; margin: 10px; position: relative;"><iframe allowfullscreen frameborder="0" style="width:640px; height:480px" src="https://lucid.app/documents/embedded/48984a30-effd-49b7-8f39-3fb6ac7ff069" id="l-GZK.nXlew7"></iframe></div>

# Referências Bibliográficas

> <a id="ref1"></a> 
>LC03-GQM-Coleta. Disponível em: https://aprender3.unb.br/pluginfile.php/3230283/mod_folder/content/0/LC03-GQM-Coleta.pdf?forcedownload=1. Acesso em: 14 de outubro de 2025.

<a id="ref2"></a> 
>LC04-GQM-Interpretacao. Disponível em: https://aprender3.unb.br/pluginfile.php/3230283/mod_folder/content/0/LC04-GQM-Interpretacao.pdf?forcedownload=1. Acesso em: 14 de outubro de 2025


## Histórico de Versões

| Versão | Data       | Descrição                                              | Autor                                                                 | Revisor |
|:------:|:----------|:-------------------------------------------------------|:----------------------------------------------------------------------|:-------:|
| 1.0    | 12/10/2025 | Criação do documento inicial e adição do conteúdo      | [João Pedro Costa](https://github.com/johnaopedro)                    | —       |
| 1.1    | 14/10/2025 | Adição de referência bibliográfica| [Fernanda Vaz Duarte dos Santos](https://github.com/)                 | —       |
| 1.2    | 14/10/2025 | Adição de métricas| [Marcella S Anderle](https://github.com/marcellaanderle)                 | —       |