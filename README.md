# - Arquitetura Cloud AWS para a Abstergo  
### Projeto: Solução em Nuvem com Foco em Redução de Custos  
### Setor: Farmacêutico | Tipo: Hub de Distribuição e Comunicação  

---

## - Sobre a Empresa

**Abstergo** é uma empresa farmacêutica que atua como um hub logístico e comunicacional entre laboratórios, distribuidores, clínicas e hospitais. A empresa necessita de uma solução cloud robusta, segura e escalável para hospedar seus sistemas e bancos de dados, e interagir com APIs de parceiros e fornecedores.  

---

## - Objetivos da Solução Cloud

- Redução de custos operacionais com infraestrutura física e digital.
- Escalabilidade conforme aumento de demanda por serviços.
- Alta disponibilidade e tolerância a falhas.
- Segurança e conformidade com a LGPD e normas regulatórias do setor farmacêutico.
- Comunicação eficiente entre sistemas internos e parceiros externos via APIs.

---

## ☁- Serviços AWS Selecionados e Justificativa

| Serviço AWS               | Função Principal                                              | Foco em Corte de Custos                               |
|---------------------------|--------------------------------------------------------------|-------------------------------------------------------|
| **EC2 Spot Instances**    | Hospedagem de serviços não-críticos                          | Economia de até 90% comparado com instâncias sob demanda |
| **AWS Lambda**            | Execução de funções sob demanda (serverless)                | Paga-se apenas pelo uso. Sem custo ocioso             |
| **Amazon S3**             | Armazenamento de arquivos, documentos e backups             | Alta durabilidade, baixo custo por GB                 |
| **RDS (Aurora Serverless)** | Banco de dados relacional escalável e sob demanda        | Escala automática, ideal para picos de acesso         |
| **Amazon CloudWatch**     | Monitoramento e logs                                         | Otimiza recursos com alertas personalizados           |
| **AWS Cost Explorer**     | Monitoramento e otimização de gastos                        | Identifica desperdícios e oportunidades de corte      |
| **Amazon API Gateway**    | Criação de APIs seguras para integração com terceiros        | Custo controlado por requisição                       |
| **AWS VPC + IAM**         | Segurança e controle de acesso                              | Evita acessos indevidos e gastos por exposição        |
| **S3 Intelligent-Tiering**| Armazenamento inteligente de arquivos                       | Movimenta automaticamente para camadas mais baratas   |
| **AWS Backup**            | Gerência automatizada de backups                            | Previne perda de dados e reduz custo com scripts      |

---

## - Arquitetura Proposta (Resumo Técnico)

- Front-end Web hospedado em **S3 + CloudFront**
- Back-end em **EC2 Spot Instances**
- APIs internas e externas com **API Gateway + Lambda**
- Bancos de dados:
  - **Aurora Serverless** para dados relacionais
  - **DynamoDB** para logs e dados semi-estruturados
- Armazenamento em **S3 com Intelligent Tiering**
- Segurança via **IAM, VPC, CloudTrail e KMS**
- Monitoramento com **CloudWatch + AWS Config**
- Gestão de custos com **AWS Budgets e Cost Explorer**

---

## - Estratégias de Corte de Custos

1. **Spot Instances e Savings Plans**  
   Substituir EC2 padrão por Spot ou Reserved Instances, com descontos de até 75%.

2. **Arquitetura Serverless (Lambda + API Gateway)**  
   Sem necessidade de provisionar servidores para tarefas pequenas.

3. **S3 com Intelligent Tiering**  
   Armazenamento automático em classes mais baratas conforme frequência de acesso.

4. **Auto Scaling e Aurora Serverless**  
   Escala automática apenas quando há demanda — ideal para períodos de pico.

5. **Monitoramento de Custo (Cost Explorer + CloudWatch)**  
   Geração de alertas quando há consumo acima do esperado.

6. **Evitar Recursos Ociosos**  
   Scripts de shutdown para ambientes de desenvolvimento e teste fora do horário comercial.

7. **Consolidação de Contas e Tags**  
   Gestão por departamentos (ex: "Financeiro", "TI") com **tagging de recursos**.

---

## - Conformidade e Segurança

- **Criptografia** em repouso (S3, RDS) e em trânsito (HTTPS, TLS).
- **Logs de auditoria com CloudTrail**.
- **Backup automatizado com retenção** conforme política da ANVISA e LGPD.
- **Gerenciamento de identidade com IAM + MFA**.

---


## ✅ Conclusão

A adoção da AWS trará para a Abstergo **resiliência, performance, flexibilidade e redução significativa de custos**. A estrutura proposta é adaptável conforme o crescimento da empresa e focada na **eficiência financeira sem abrir mão da segurança e conformidade**.
