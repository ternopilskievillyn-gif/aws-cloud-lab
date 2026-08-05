# Arquitetura do AWS Cloud Lab

Este projeto tem como objetivo aplicar na prática conceitos fundamentais da Amazon Web Services (AWS).

## Arquitetura inicial

Internet
    ↓
AWS
    ↓
VPC
    ↓
Subnet Pública
    ↓
Security Group
    ↓
EC2
    ↓
Nginx
    ↓
Aplicação Web

## Objetivo

Hospedar uma aplicação web simples em uma instância Amazon EC2 utilizando Nginx como servidor web.

Durante o projeto serão praticados conceitos de:

- Amazon EC2
- Amazon VPC
- Subnets
- Security Groups
- SSH
- Linux
- Nginx
- HTTP
- Deploy
- Amazon S3
- Monitoramento de custos na AWS

## Deploy realizado

A aplicação foi hospedada em uma instância Amazon EC2 utilizando Ubuntu Linux.

O Nginx foi instalado e configurado como servidor web para disponibilizar a aplicação através da internet.

### Acesso à aplicação

O acesso HTTP foi permitido através do Security Group utilizando:

- Protocolo: TCP
- Porta: 80
- Origem: 0.0.0.0/0

O acesso administrativo à instância é realizado via SSH pela porta 22, restrito ao IP autorizado.

### Fluxo da aplicação

Usuário
    ↓
Internet
    ↓
Security Group (HTTP - porta 80)
    ↓
Amazon EC2
    ↓
Ubuntu Linux
    ↓
Nginx
    ↓
Aplicação Web

## Amazon S3

Foi criado um bucket Amazon S3 para praticar armazenamento de objetos na nuvem.

Configurações utilizadas:

- Bucket de uso geral
- Bloqueio de acesso público habilitado
- Versionamento desabilitado
- Criptografia padrão SSE-S3

Foi realizado o upload do arquivo `01-website-ec2.png` para validar o armazenamento de objetos.

Ao testar a URL pública do objeto, o acesso foi negado (`AccessDenied`), confirmando que o bucket não permite acesso público.