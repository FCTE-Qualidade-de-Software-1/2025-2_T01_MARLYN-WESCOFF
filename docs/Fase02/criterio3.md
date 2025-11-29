# Critério 3: Execução da Avaliação - Segurança

## 1. Goal (Objetivo)<a href="#ref1"><sup>1</sup></a>

| Analisar | o aplicativo Guardiões da Saúde |
|----------|--------------------------------|
| Para o propósito de | Avaliar |
| Com respeito a | A *segurança* |
| Do ponto de vista da | Da equipe de desenvolvimento |
| No contexto da | Disciplina de Qualidade de Software (FCTE - UnB) |

## 2. Questions (Questões) e 3. Metrics (Métricas)

### Confidencialidade

#### Q1: Os dados de saúde estão protegidos contra acesso não autorizado?

**Hipóteses:**

> - **H1.1:** O sistema utiliza criptografia para comunicações entre cliente e servidor.

#### Q2: O sistema segue práticas de desenvolvimento seguro?

**Hipóteses:**

> - **H2.1:** O código é revisado periodicamente para identificar vulnerabilidades.
> - **H2.2:** O sistema utiliza ferramentas automatizadas de análise de código.
> - **H2.3:** Existe processo documentado para correção de vulnerabilidades.

#### Q3: Os dados sensíveis armazenados localmente estão criptografados?

**Hipóteses:**

> - **H3.1:** Nenhum dado pessoal é armazenado em texto claro.
> - **H3.2:** O app utiliza criptografia AES ou Android Keystore.

**Métricas:**

---

### M1.1 — Utilização de HTTPS
!!! info "Detalhes da Métrica"
    - **Objetivo:** Verificar se todas as comunicações utilizam HTTPS/TLS.
    - **Fórmula:**  
      **(Endpoints com HTTPS / Endpoints testados) × 100**
    - **Periodicidade:** Avaliação a cada ciclo de release ou sempre que novos endpoints forem incluídos.
    - **Valor-alvo:** 100% das comunicações com HTTPS.
    - **Coleta:**  
        1. Verificar se todos os endpoints respondem exclusivamente via HTTPS.  
        2. Validar certificados SSL/TLS (CA confiável, data de validade, cadeia completa).  
        3. Confirmar suporte a protocolos seguros (TLS 1.2+).  
        4. Identificar versões de cifra utilizadas (cipher suites).  
    - **Responsável:** Equipe de Desenvolvimento / Segurança da Informação.
**Responsável:** Equipe de Desenvolvimento / Segurança da Informação.

---

### M2.1 — Documentação de Vulnerabilidades
!!! info "Detalhes da Métrica"
    - **Objetivo:** Verificar o processo de documentação de vulnerabilidades
    - **Fórmula:** Nº de pull requests ou issues com label "fix"
    - **Periodicidade:** ???
    - **Valor-alvo:** ???
    - **Coleta:** 
            - 1. Acessar repositório do projeto
            - 2. Filtrar PRs/issues com label "fix"
            - 3. Documentar quantidade encontrada
    - **Responsável:** Equipe de Desenvolvimento

---

### M3.1 — Armazenamento Local Seguro
!!! info "Detalhes da Métrica"
    - **Objetivo:** Medir o percentual de dados sensíveis criptografados
    - **Fórmula:** (Nº de variáveis sensíveis criptografadas / Nº total de variáveis sensíveis) × 100
    - **Periodicidade:** Semanal
    - **Valor-alvo:** ≥ 100%
    - **Coleta:** 
            - 1. Mapear todas as variáveis sensíveis armazenadas localmente
            - 2. Verificar criptografia por análise de código
            - 3. Documentar total e quantidade criptografada
    - **Responsável:** Equipe de Desenvolvimento

---

### M3.2 — Tempo de Descriptografia
!!! info "Detalhes da Métrica"
    - **Objetivo:** Medir o tempo médio de descriptografia de dados locais
    - **Fórmula:** Média dos tempos de descriptografia
    - **Periodicidade:** Semanal
    - **Valor-alvo:** ≤ 1s
    - **Coleta:** 
            - 1. Selecionar conjunto representativo de dados criptografados
            - 2. Medir tempo com ferramentas de profiling (mínimo 10 amostras)
            - 3. Calcular média dos tempos obtidos
    - **Responsável:** Equipe de Desenvolvimento

---

### Integridade

#### Q4: Os dados estão protegidos contra alteração não autorizada?

**Hipóteses:**

> - **H4.1:** Mecanismos de validação detectam alterações não autorizadas.
> - **H4.2:** Modificações em dados críticos geram alerta imediato.

#### Q5: Existem mecanismos para garantir consistência e rastreabilidade dos dados?

**Hipóteses:**

> - **H5.1:** Operações críticas são registradas em logs de auditoria.
> - **H5.2:** O histórico permite rastrear e restaurar dados.

**Métricas:**

---

### M4.1 — Alertas de Integridade
!!! info "Detalhes da Métrica"
    - **Objetivo:** Garantir que o sistema identifique e bloqueie modificações não autorizadas nos dados em trânsito.
    - **Fórmula:**  
      **(Tentativas de manipulação bloqueadas / Tentativas de manipulação testadas) × 100**
    - **Periodicidade:** Em cada ciclo de release ou após mudanças em validações, regras de negócio ou endpoints sensíveis.
    - **Valor-alvo:** 100% das modificações não autorizadas devem ser bloqueadas.
    - **Coleta:**  
        1. Verificar mecanismos de verificação de integridade (validações server-side, regras de domínio, autenticação e autorização).  
        2. Executar cenários de ataque simulados (alteração de IDs, timestamps, flags administrativas, escalonamento de privilégio, etc.).  
        3. Registrar e documentar o comportamento da API (HTTP 401/403/422).  
    - **Responsável:** Equipe de Desenvolvimento / Segurança da Informação.

---

### M5.1 — Rastreabilidade de Operações
!!! info "Detalhes da Métrica"
    - **Objetivo:** Assegurar rastreabilidade de operações críticas
    - **Fórmula:** ???
    - **Periodicidade:** ???
    - **Valor-alvo:** ???
    - **Coleta:** 
            - 1. Identificar operações críticas no sistema
            - 2. Verificar existência de logs para cada operação
            - 3. Documentar cobertura de logs
    - **Responsável:** Equipe de Desenvolvimento

---

## Diagrama -  Segurança

<div style="width: 640px; height: 480px; margin: 10px; position: relative;"><iframe allowfullscreen frameborder="0" style="width:640px; height:480px" src="https://lucid.app/documents/embedded/48984a30-effd-49b7-8f39-3fb6ac7ff069" id="l-GZK.nXlew7"></iframe></div>

# Referências Bibliográficas

> <a id="ref1"></a> 
> LC03-GQM-Coleta. Disponível em: https://aprender3.unb.br/pluginfile.php/3230283/mod_folder/content/0/LC03-GQM-Coleta.pdf?forcedownload=1. Acesso em: 14 de outubro de 2025.

> <a id="ref2"></a> 
> LC04-GQM-Interpretacao. Disponível em: https://aprender3.unb.br/pluginfile.php/3230283/mod_folder/content/0/LC04-GQM-Interpretacao.pdf?forcedownload=1. Acesso em: 14 de outubro de 2025.

## Histórico de Versões

| Versão | Data       | Descrição                                              | Autor                                                                 | Revisor |
|:------:|:----------|:-------------------------------------------------------|:----------------------------------------------------------------------|:-------:|
| 1.0    | 12/10/2025 | Criação do documento inicial e adição do conteúdo      | [João Pedro Costa](https://github.com/johnaopedro)                    | —       |
| 1.1    | 14/10/2025 | Adição de referência bibliográfica                     | [Fernanda Vaz Duarte dos Santos](https://github.com/)                 | —       |
| 1.2    | 14/10/2025 | Adição de métricas                                     | [Marcella S Anderle](https://github.com/marcellaanderle)              | —       |
| 1.3    | 15/10/2025 | Adição de métricas e Correção                          | [Vinícius Rufino](https://github.com/RufinoVfR)                       | —       |
| 1.4    | 23/10/2025 | Ajustes no tópico 2.3                                  | [Marcella S Anderle](https://github.com/marcellaanderle)              | —       |
| 1.5   | 24/10/2025 | melhoria na padronização  e diagrama                                | [Fernanda vaz ](https://github.com/Fernandavazgit1)              | —       |
| 1.6   | 24/10/2025 | Ajuste topicos m1.1 e m4.1                                | [Oscar de Brito ](https://github.com/OscarDeBrito)              | —       |



<!--
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
-->
