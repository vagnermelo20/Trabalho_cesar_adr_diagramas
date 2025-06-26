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












Descrição dos Componentes:

Interface Web/Mobile (UI): O ponto de interação do cliente com a plataforma FortunaTech, onde ele gerencia suas finanças e concede consentimentos.
API Gateway: Ponto de entrada único para todas as requisições, roteando-as para os serviços internos apropriados e garantindo a segurança.
Serviços Core da FortunaTech: Representa a lógica de negócio existente da FortunaTech, como gestão de clientes, contas internas e produtos.
Motor de Análise e IA: Componente responsável por processar os dados (internos e externos) para realizar análises de risco de crédito, gerar recomendações de investimento personalizadas e fornecer insights proativos. 

Módulo de Integração Open Finance: Componente central para a nova estratégia. Ele é responsável por toda a comunicação com o ecossistema Open Finance:
Gerencia a autenticação e autorização (OAuth2).
Orquestra a obtenção do consentimento do cliente.
Consome as APIs de dados de outras instituições.
Invoca as APIs de iniciação de pagamento.
Garante a conformidade com os padrões de segurança e regulamentação. 
APIs de Outras Instituições (IFs): Interfaces externas padronizadas, providas por outros bancos e fintechs, de onde a FortunaTech obterá os dados e através das quais iniciará os pagamentos. 

Diretório de Participantes: Serviço centralizado do ecossistema Open Finance que lista todas as instituições participantes e suas capacidades de API, consultado pelo Módulo de Integração.

