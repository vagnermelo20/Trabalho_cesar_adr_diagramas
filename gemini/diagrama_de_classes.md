```mermaid
classDiagram
    direction LR

    class Cliente {
        +ID_Cliente
        +Nome
        +Tipo_Pessoa (PME, Autônomo)
        +obterConsentimento()
    }

    class PlataformaFortunaTech {
        +oferecerHubFinanceiro()
        +iniciarPagamento()
    }

    class ProdutoFinanceiro {
        <<abstract>>
        +ID_Produto
        +Descricao
    }

    class Credito {
        +Valor
        +TaxaJuros
        +StatusAprovacao
        +analisarRiscoComOpenFinance()
    }

    class Investimento {
        +TipoInvestimento
        +ValorAplicado
        +Rentabilidade
        +recomendarComBasePortfolioCompleto()
    }

    class Consentimento {
        +ID_Consentimento
        +DataExpiracao
        +Status (Ativo, Revogado)
        +Permissoes (DadosCadastrais, DadosTransacionais)
        +validar()
    }

    class DadosExternos {
        +ID_Dados
        +Fonte (Nome da IF)
        +TipoDado (Saldo, Transação, Investimento)
        +Conteudo
    }

    class IniciacaoPagamento {
        +ID_Pagamento
        +Valor
        +Destinatario
        +Status (Pendente, Confirmado, Falhou)
        +executarTransferencia()
    }

    Cliente "1" -- "0..*" ProdutoFinanceiro : possui
    Cliente "1" -- "1..*" Consentimento     : concede
    PlataformaFortunaTech "1" -- "0..*" Cliente : atende
    ProdutoFinanceiro <|-- Credito
    ProdutoFinanceiro <|-- Investimento
    PlataformaFortunaTech ..> Consentimento     : gerencia
    PlataformaFortunaTech ..> IniciacaoPagamento : processa
    Consentimento "1" -- "0..*" DadosExternos  : autoriza_acesso
