# Diagrama da Arquitetura

```mermaid
flowchart TD
    USER[Usuário / Navegador]
    INTERNET[Internet]

    subgraph AWS[Amazon Web Services]
        subgraph VPC[Amazon VPC]
            SUBNET[Subnet Pública]
            SG[Security Group]
            EC2[Amazon EC2 - Ubuntu]
            NGINX[Nginx]
            APP[Aplicação Web]
            EBS[Amazon EBS - gp3]
        end

        S3[Amazon S3]
    end

    USER -->|HTTP - Porta 80| INTERNET
    INTERNET --> SG
    SG --> EC2
    SUBNET --> EC2
    EC2 --> NGINX
    NGINX --> APP
    EBS --- EC2

    APP -. Arquivos / Objetos .-> S3