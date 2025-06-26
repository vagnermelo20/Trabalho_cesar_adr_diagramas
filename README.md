# ADR

# Documento de Arquitetura – FortunaTech & Open Finance

Este documento descreve as decisões e a arquitetura de alto nível para a integração da plataforma FortunaTech com o ecossistema do Open Finance no Brasil.

---

## Registro de Decisão de Arquitetura (ADR)

### ADR-001: Adoção e Integração com o Ecossistema Open Finance Brasil

- **Status**: Proposto  
- **Data**: 26/06/2025  
- **Decisor**: CTO, Liderança de Produto da FortunaTech  

---

### 1. Contexto

A FortunaTech enfrenta desafios relacionados à visão limitada dos dados financeiros de seus clientes, o que impacta a precisão da análise de risco e a personalização de produtos. Com o aumento da concorrência, a adoção de novas tecnologias como o Open Finance tornou-se uma oportunidade estratégica para inovar e fortalecer a posição da empresa no mercado.

---

### 2. Decisão

A FortunaTech decidiu adotar e integrar sua plataforma com o ecossistema do Open Finance no Brasil. A empresa atuará como receptora de dados e iniciadora de pagamentos, consumindo as APIs padronizadas para acessar dados de outras instituições (com o consentimento do cliente) e para iniciar transações financeiras diretamente de sua plataforma.

---

### 3. Consequências

#### Positivas

- **Melhora na Análise de Risco**  
  Análises de crédito mais precisas com base em um panorama financeiro completo.

- **Criação de Produtos Inovadores**  
  Desenvolvimento de um “hub financeiro” com agregadores de investimentos e comparadores de crédito.

- **Melhora da Experiência do Usuário**  
  Gestão financeira centralizada e simplificação de pagamentos e transferências.

- **Aumento da Competitividade**  
  Posicionamento como pioneira na oferta de soluções baseadas em dados abertos.

#### Negativas (Riscos e Desafios)

- **Complexidade de Implementação**  
  Exige esforço técnico significativo para integração e conformidade regulatória.

- **Segurança e Conformidade**  
  Necessidade de investimentos robustos em segurança para conformidade com a LGPD e regulamentações do Banco Central.

- **Custos de Desenvolvimento**  
  Custos associados ao desenvolvimento inicial e à manutenção contínua da integração.

- **Gestão de Consentimento**  
  Demanda de um sistema robusto e transparente para gerenciar o consentimento dos clientes.




## diagrama de classes

![image](https://github.com/user-attachments/assets/4a003d17-062b-4f4d-bffe-9ed526dad249)

## diagrama de componentes

![image](https://github.com/user-attachments/assets/168dc263-6744-4bee-a490-1f42d9309875)
