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
        <<Abstract>>
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
    Cliente "1" -- "1..*" Consentimento : concede
    PlataformaFortunaTech "1" -- "1" Cliente : atende
    ProdutoFinanceiro <|-- Credito
    ProdutoFinanceiro <|-- Investimento
    PlataformaFortunaTech ..> Consentimento : gerencia
    PlataformaFortunaTech ..> IniciacaoPagamento : processa
    Consentimento "1" -- "0..*" DadosExternos : autoriza_acesso









Descrição das Classes:

Cliente: Representa os usuários da FortunaTech (PMEs e autônomos).  É a entidade que concede o consentimento para o compartilhamento de dados.
PlataformaFortunaTech: Representa a interface principal da fintech, que se tornará o "hub financeiro". 
ProdutoFinanceiro: Classe abstrata para os diferentes produtos oferecidos, como Crédito e Investimento. 
Credito: Especialização de ProdutoFinanceiro. O método analisarRiscoComOpenFinance() reflete a capacidade de usar dados externos para uma análise mais precisa. 
Investimento: Outra especialização. O método recomendarComBasePortfolioCompleto() indica a consultoria personalizada com base em dados de outras instituições. 
Consentimento: Entidade crucial que formaliza a permissão do cliente para o acesso aos seus dados, conforme as regras do Open Finance. 

DadosExternos: Representa os dados financeiros do cliente obtidos de outras instituições via Open Finance. 

IniciacaoPagamento: Modela a funcionalidade de iniciar pagamentos e transferências a partir da plataforma da FortunaTech, usando fundos de contas externas. 