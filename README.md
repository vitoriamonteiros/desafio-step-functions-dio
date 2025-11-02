# Desafio AWS Step Functions

## Objetivo do Projeto
Este projeto tem como objetivo explorar o serviço AWS Step Functions, criando workflows automatizados que integram diferentes serviços da AWS, como Lambda, S3, SNS, SQS e DynamoDB. com foco em aplicar conceitos de **orquestração, automação e boas práticas de arquitetura em nuvem**.

---

## Serviços Utilizados

- **AWS Step Functions**: Orquestração do fluxo de trabalho.  
- **AWS Lambda**: Funções para validar arquivos e processar dados.  
- **Amazon S3**: Armazenamento de arquivos de entrada.  
- **Amazon SNS**: Envio de notificações em caso de erro ou sucesso.  
- **Amazon DynamoDB / SQS**: Armazenamento ou envio de mensagens processadas (dependendo do fluxo).  

---

## Descrição do Workflow
O workflow criado segue a seguinte lógica:

1. **Upload do arquivo no S3**: Evento que dispara a execução do Step Functions.  
2. **Validação do arquivo**: Lambda verifica se o arquivo atende aos critérios necessários (formato, tamanho ou dados específicos).  
3. **Notificação via SNS**: Caso haja erro na validação, uma notificação é enviada.  
4. **Processamento e armazenamento**: Arquivos válidos são processados e registrados no DynamoDB ou enviados para fila SQS.  
5. **Monitoramento**: Todas as etapas são monitoradas pelo Step Functions, permitindo acompanhar o status da execução.  

---

## Aprendizados
- Compreendi como **Step Functions** facilita a integração de múltiplos serviços sem a necessidade de gerenciar servidores manualmente.  
- Importância de **definir triggers e falhas corretamente** para que o workflow não pare em caso de erro.  

---

## Próximos Passos
- Implementar **triggers adicionais**, como eventos de tempo ou atualizações de banco de dados.  
- Automatizar o envio de logs detalhados para CloudWatch.  
- Explorar integrações mais avançadas com Lambda e SQS para cenários complexos de mensageria.  

