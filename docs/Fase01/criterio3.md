# Tipo de produto e descrição estruturada do software

## Sobre o Projeto

- **Nome:** Guardiões da Saúde 
- **Descrição:** Plataforma de saúde participativa para coleta, monitoramento e análise de dados em saúde, apoiando a vigilância epidemiológica comunitária.  
- **Instituição:** UnB - Universidade de Brasília 
- **Repositórios:**  
  - [Guardiões App (Frontend)](#ref3)
  - [Guardiões API (Backend)](#ref2) 
- **Página oficial (Play Store):** [Guardiões da Saúde](#ref1)
- **Grupo:** ProEpi Desenvolvimento  

## Classificação do Tipo de Produto  

O Guardiões da Saúde é um aplicativo móvel gratuito, disponível para Android e iOS, voltado para a vigilância em saúde. Ele segue o paradigma da [vigilância participativa](#ref4), no qual a comunidade não atua apenas como receptora de informações, mas participa ativamente do processo de monitoramento epidemiológico. Também pode ser utilizado em contextos institucionais, ampliando seu alcance para órgãos e serviços de saúde pública.

A participação é feita de forma voluntária: cada usuário pode registrar sintomas e seu estado de saúde, criando um diário que contribui para análises epidemiológicas em tempo real. Esse formato reforça a ideia de [ciência cidadã](#ref5), em que a própria população ajuda a produzir e usar informações relevantes para a saúde coletiva.

Do ponto de vista técnico, o Guardiões da Saúde adota uma [arquitetura cliente-servidor](#ref6). O aplicativo funciona como frontend, oferecendo a interface para coleta e consulta de dados, enquanto o backend, acessado por meio de uma API, processa as requisições, organiza as informações e disponibiliza recursos como dashboards de monitoramento e gerenciamento de perfis.

Esse backend se conecta a um banco de dados central, onde ficam armazenados os relatos enviados, históricos de sintomas, dados de geolocalização e informações associadas aos perfis dos usuários. Como lida com dados sensíveis, o sistema exige especial atenção a aspectos de segurança, garantindo consentimento, anonimização e proteção da privacidade, em conformidade com boas práticas da área.

# Referências Bibliográficas

As informações sobre o propósito da avaliação foram obtidas nas seguintes fontes:

> <a id="ref1"></a> GUARDIÕES DA SAÚDE. **Guardiões da Saúde**. [Aplicativo]. Disponível em: [https://play.google.com/store/apps/details?id=com.guardioesapp\&hl=pt\_BR](https://play.google.com/store/apps/details?id=com.guardioesapp&hl=pt_BR). Acesso em: 28 set. 2025.

> <a id="ref2"></a> PROEPIDDESENVOLVIMENTO. **Guardiões API (Backend)**. GitHub, 2025. Disponível em: [https://github.com/ProEpiDesenvolvimento/guardioes-api](https://github.com/ProEpiDesenvolvimento/guardioes-api). Acesso em: 28 set. 2025.

> <a id="ref3"></a> PROEPIDDESENVOLVIMENTO. **Guardiões App (Frontend)**. GitHub, 2025. Disponível em: [https://github.com/ProEpiDesenvolvimento/guardioes-app](https://github.com/ProEpiDesenvolvimento/guardioes-app). Acesso em: 28 set. 2025.
> <a id="ref4"></a> PROEPIDDESENVOLVIMENTO. **Guardiões da Saúde**. ProEpi, 2025. Disponível em: [https://proepi.org.br/guardioes-da-saude/](https://proepi.org.br/guardioes-da-saude/). Acesso em: 01 out. 2025.
> <a id="ref5"></a> PROEPIDDESENVOLVIMENTO. **Guardiões API**. GitHub, 2025. Disponível em: [https://github.com/ProEpiDesenvolvimento/guardioes-api](https://proepidesenvolvimento.github.io/guardioes-api/#api). Acesso em: 01 out. 2025.
> <a id="ref6"></a> SIBBR. **Sistema de Informação sobre a Biodiversidade Brasileira**. Gov.br, 2025. Disponível em: [https://www.sibbr.gov.br/cienciacidada/oquee.html](https://www.sibbr.gov.br/cienciacidada/oquee.html). Acesso em: 01 out. 2025.

## Histórico de Versões

| Versão | Data       | Descrição                         | Autor                               | Revisor |
|:------:|:----------|:----------------------------------|:-------------------------------------|:-------:|
| 1.0    | 28/09/2025 | Criação do Documento inicial e adição do conteudo | [João Pedro Costa](https://github.com/johnaopedro) |   —     |
| 1.1    | 30/09/2025 | Ajustando as referências bibliográficas | [João Pedro Costa](https://github.com/johnaopedro) |   —     |
| 1.2    | 01/10/2025 | Adicionando Classificação do Tipo de Produto | [Vinícius Rufino](https://github.com/RufinoVfR) |   —     |