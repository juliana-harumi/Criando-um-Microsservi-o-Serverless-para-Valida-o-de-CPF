# Criando um Microsserviço Serverless para Validação de CPF com Azure

## Introdução  
Validar CPFs é uma necessidade comum em aplicações que exigem cadastro de usuários no Brasil. Um microsserviço dedicado a esta tarefa simplifica a validação, centraliza a lógica de negócio e torna o sistema mais modular. Neste repositório, vamos explorar como criar um microsserviço serverless para validação de CPF utilizando o **Azure Functions**, uma solução eficiente e econômica que se adapta automaticamente à demanda.

---

## Objetivo  
O objetivo deste projeto é implementar um microsserviço escalável e de baixo custo que:  
- Valide se um CPF é válido conforme o algoritmo oficial.  
- Forneça uma API REST para validação via chamadas HTTP.  
- Garanta alta disponibilidade e performance utilizando a infraestrutura serverless da Azure.  

---

## Tecnologias Utilizadas  
- **Azure Functions** - Serviço serverless para execução de código.  
- **Azure API Management** - Para expor e gerenciar a API de forma segura.  
- **Azure Monitor** - Para monitorar o desempenho e as métricas do serviço.  
- **Linguagem de programação** - **Node.js** (pode ser adaptado para Python, C# ou outra linguagem suportada).  

---

## Arquitetura da Solução  

1. **Requisição HTTP**: O cliente faz uma requisição HTTP com o CPF a ser validado.  
2. **Azure Function**: Recebe a requisição, executa a lógica de validação do CPF e retorna o resultado.  
3. **API Management**: Expondo a Azure Function de maneira segura e escalável.  
4. **Monitoramento**: Logs e métricas armazenados no Azure Monitor para análise de performance.  

---

## Implementação  

### 1. Criando a Azure Function  
1. Instale o [Azure Functions Core Tools](https://learn.microsoft.com/azure/azure-functions/functions-run-local) e o [Azure CLI](https://learn.microsoft.com/cli/azure/install-azure-cli).  
2. No terminal, execute:  
   ```bash
   func init validar-cpf --worker-runtime node
   cd validar-cpf
   func new --name ValidarCPF --template "HTTP trigger"
