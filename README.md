# Projeto-Final
-----
O projeto proposto pela equipe da Compass UOL <img src="https://logospng.org/download/uol/logo-uol-icon-1024.png" alt="Ícone da UOL" width="15"> que consiste na migração de uma estrutura para o serviço AWS <img src="https://www.svgrepo.com/show/394021/aws.svg" alt="Ícone da AWS" width="15"> , a início de forma **As-Is** e assim uma modernização posterior.


## Sumário
- [Introdução](#introdução)
- [Arquitetura Atual](#arquitetura-atual)
- [Arquitetura Proposta](#arquitetura-proposta)
- [Imagens de Referência](#imagens-de-referência)

## Introdução
Este documento detalha a transição de uma arquitetura legada para uma solução modernizada em AWS. A seguir, são apresentados os diagramas que ilustram a arquitetura atual e a proposta de modernização.

## Arquitetura Atual

A arquitetura atual consiste em uma aplicação monolítica, com os seguintes componentes:

- **db01 (MySQL)**: Servidor de banco de dados.
- **back01 (APIs)**: Servidor que hospeda as APIs.
- **front01 (Web)**: Servidor que hospeda a aplicação web.

### Processos de Migração
Os serviços AWS utilizados para a migração incluem:

- **AWS DMS (Database Migration Service)**: Para migração do banco de dados MySQL.
- **AWS Server Migration Service**: Para migração dos servidores front01 e back01.

#### Diagrama da Arquitetura Atual:
![Arquitetura Atual](image1.png)

---

## Arquitetura Proposta

Na arquitetura modernizada, a aplicação é executada em um ambiente altamente escalável e gerenciado na AWS. Os principais componentes são:

- **Amazon EKS (Kubernetes Gerenciado)**: Hospeda a aplicação em clusters Kubernetes.
- **Amazon RDS**: Gerencia o banco de dados MySQL de forma escalável e resiliente.
- **EFS (Elastic File System)**: Disponibiliza armazenamento compartilhado para as instâncias do backend.
- **Network Load Balancer**: Faz a distribuição de tráfego para os pods em execução no cluster.
- **CloudFront, WAF e Route 53**: Gerenciam a distribuição global, segurança e roteamento DNS.

#### Diagrama da Arquitetura Proposta:
![Arquitetura Proposta](image2.png)

---

## Imagens de Referência

- **Arquitetura Atual:**
![Arquitetura Atual](image1.png)

- **Arquitetura Proposta:**
![Arquitetura Proposta](image2.png)

---

## Considerações Finais
A modernização para uma arquitetura baseada em Kubernetes e serviços gerenciados da AWS traz benefícios como escalabilidade, resiliência e eficiência operacional. Este documento serve como referência para implementação e futuras melhorias.

