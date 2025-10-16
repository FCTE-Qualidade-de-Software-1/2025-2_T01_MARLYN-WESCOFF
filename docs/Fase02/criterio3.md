# Critério 3: Execução da Avaliação - Segurança

## 1. Goal (Objetivo)<a href="#ref1"><sup>1</sup></a>


| Analisar | o aplicativo Guardiões da Saúde |
|----------|--------------------------------|
| Para o propósito de | Avaliar |
| Com respeito a | A *segurança* |
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

**Q3:** Os dados sensíveis armazenados localmente no dispositivo (cache, preferências) estão devidamente criptografados?

**Hipóteses:**

  - **1:** Nenhum dado pessoal é armazenado em texto claro.
  - **2:** O app utiliza criptografia AES ou Android Keystore.

**Métricas:**

- **1: Utilização de comunicação utiliza HTTPS**
  - **Objetivo:** Verificar se todas as comunicações entre cliente e servidor utilizam HTTPS/TLS para garantir a proteção dos dados em trânsito.
  - **Método de coleta:** Verificar a configuração do servidor incluindo: Certificados SSL/TLS válidos. Protocolos suportados (ex.: TLS 1.2 ou superior).
  <!--Não foi possível verificar devido ao código do sistema não ter caminhos públicos para conferir se utiliza comunicação HTTPS-->
 

- **2: Documentação para tratamento e correção de vulnerabilidades identificadas**
  - **Objetivo:** Verificar o processo de documentação.
  - **Método de coleta:** Verificar nº de pull requests ou issues com a label fix.

---

### 3.1: – Armazenamento Local Seguro
!!! info "Detalhes da Métrica"
    - **Objetivo:** medir o percentual de dados criptografados 
    - **Fórmula:**: Nº de variáveis sensíveis criptografadas / Nº total de variáveis sensíveis
    - **Periodicidade:**  semanal
    - **Valor-alvo:** ≥ 100%
    - **Coleta:** 

            - 1. Mapear todas as variáveis sensíveis armazenadas localmente (como tokens, credenciais, informações de saúde).
            - 2. Verificar, por meio de análise de código e inspeção em tempo de execução, se cada variável está protegida por algoritmo de criptografia.
            - 3. Documentar a quantidade total de variáveis e quantas estão devidamente criptografadas.

    - **Responsável:** Equipe de  Desenvolvimento

---

### 3.2: – Armazenamento Local Seguro
!!! info "Detalhes da Métrica"
    - **Objetivo:** medir o tempo médio de descriptografia 
    - **Fórmula:**: média do tempo para descriptografar dados locais
    - **Periodicidade:**  semanal
    - **Valor-alvo:** ≤ 1s
    - **Coleta:** 

            - 1. Selecionar um conjunto representativo de dados criptografados (como tokens, dados de sessão, preferências locais).
            - 2. Medir o tempo de execução das rotinas de descriptografia por meio de ferramentas de profiling ou logs de desempenho.
            - 3. Calcular a média dos tempos obtidos durante múltiplas execuções (mínimo de 10 amostras).

    - **Responsável:** Equipe de  Desenvolvimento

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
      - 1. O controle de acesso e a criptografia de dados estão bem implementados, o que é positivo.
      
- **Pontos de Melhoria:**
      - 1. Os logs devem ser revisados para eliminar qualquer dado sensível armazenado inadvertidamente.
      - 2. Criar módulo centralizado de logs com anonimização e retenção limitada.

### 5.2 Integridade
- **Pontos Fortes:**
- **Pontos de Melhoria:**


## 6. Ações de Melhoria

        - 1. Revisar os logs com a intenção de eliminar dados sensíveis armazenados de forma indevida;
        - 2.  Implementar uma ferramenta (SAST - Static Application Security Testing) para varredura contínua.


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
| 1.3    | 15/10/2025 | Adição de métricas e Correção| [Vinícius Rufino](https://github.com/RufinoVfR)                 | —       |
