# 🚀 Desafio: Infraestrutura Automatizada com AWS CloudFormation

## 🧩 Sobre o Projeto
Este repositório faz parte do desafio proposto pela **DIO (Digital Innovation One)**, com o objetivo de colocar em prática os conceitos de **Infraestrutura como Código (IaC)** utilizando o **AWS CloudFormation**.  

O propósito principal é **automatizar a criação de recursos na AWS**, aplicando boas práticas de versionamento e documentação no **GitHub**.

---

## 🎯 Objetivos de Aprendizagem
Ao final deste desafio, espera-se demonstrar:

- Aplicação prática dos conceitos aprendidos sobre **CloudFormation**;
- Documentação clara e organizada de processos técnicos;
- Uso do **GitHub** como ferramenta de colaboração e portfólio técnico.

---

## 🛠️ Tecnologias e Serviços Utilizados
- **AWS CloudFormation**
- **Amazon EC2**
- **Amazon S3**
- **Amazon VPC**
- **IAM (Identity and Access Management)**
- **Git e GitHub**
- **Markdown** para documentação

> ⚙️ *Os serviços podem variar conforme a proposta do laboratório. A lista acima reflete um cenário comum em desafios de IaC com AWS.*

---

## 🧠 Passo a Passo da Implementação 

> Esta seção descreve o fluxo seguido para criação e automação da infraestrutura.

1. **Planejamento da Arquitetura**
   - Definição dos recursos necessários (EC2, S3, Security Groups, etc.)
   - Estruturação em formato YAML com parâmetros, recursos e saídas.

2. **Criação do Template**
   - Desenvolvimento do arquivo `main-template.yaml` com blocos:
     - `Parameters`: variáveis configuráveis (ex: nome da instância, tipo, AMI).
     - `Resources`: definição dos serviços que serão criados.
     - `Outputs`: dados retornados após a execução (ex: IP público da EC2).

3. **Validação do Template**
   - Utilização do comando:
     ```bash
     aws cloudformation validate-template --template-body file://main-template.yaml
     ```

4. **Implantação (Deploy)**
   - Execução do stack via CLI ou console:
     ```bash
     aws cloudformation create-stack --stack-name desafio-stack --template-body file://main-template.yaml
     ```

5. **Verificação dos Recursos**
   - Acompanhamento da criação no console AWS e confirmação das saídas definidas no template.

---

## 🧾 Exemplo de Estrutura do Template

```yaml
AWSTemplateFormatVersion: "2010-09-09"
Description: "Template para criação de uma instância EC2 simples"

Parameters:
  KeyName:
    Description: "Nome da chave SSH para acesso à instância"
    Type: String

Resources:
  EC2Instance:
    Type: "AWS::EC2::Instance"
    Properties:
      InstanceType: t2.micro
      ImageId: ami-0c55b159cbfafe1f0
      KeyName: !Ref KeyName

Outputs:
  InstanceId:
    Description: "ID da instância criada"
    Value: !Ref EC2Instance
💡 Insights e Aprendizados

Durante o estudo e construção deste desafio, pude reforçar conceitos como:

Importância do versionamento de infraestrutura;

Benefícios da reprodutibilidade e da automação no provisionamento de ambientes;

Clareza e manutenção facilitada por meio de documentação estruturada em Markdown;

O papel do CloudFormation como ferramenta fundamental em ambientes DevOps.

📚 Referências

Documentação Oficial AWS CloudFormation

Guia de Markdown do GitHub

Formação GitHub Certification - GitBook

