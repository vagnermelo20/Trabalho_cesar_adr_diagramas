```mermaid
graph TD
    subgraph "Plataforma FortunaTech"
        direction LR
        UI_WebMobile["Interface Web/Mobile"]
        APIGateway["API Gateway"]
        CoreServices["Serviços Core da FortunaTech"]
        ModuloAnalise["Motor de Análise e IA"]
        ModuloOpenFinance["Módulo de Integração Open Finance"]

    end

    subgraph "Ecossistema Externo"
        direction LR
        APIsExternas["APIs de Outras Instituições (IFs)"]
        DiretorioOpenFinance["Diretório de Participantes (Open Finance)"]
    end

    UI_WebMobile -- Requisições HTTP/S --> APIGateway
    APIGateway -- Chamadas de serviço --> CoreServices
    CoreServices -- Solicita análise --> ModuloAnalise
    CoreServices -- Solicita dados/pagamentos --> ModuloOpenFinance

    ModuloAnalise -- Consome dados de --> CoreServices
    ModuloAnalise -- Gera insights --> CoreServices

    ModuloOpenFinance -- Consulta de participantes --> DiretorioOpenFinance
    ModuloOpenFinance -- Requisições de dados/pagamentos (API) --> APIsExternas

    style ModuloOpenFinance fill:#f9f,stroke:#333,stroke-width:2px
