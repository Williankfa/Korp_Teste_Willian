# Korp_Teste_Willian
Teste Técnico Korp - Integração de Microsserviços de Estoque (C#) e Faturamento (C#) com Frontend em Angular.


# Teste Técnico Korp - Sistema de Microsserviços (Estoque e Faturamento)
Este projeto consiste em uma solução de microsserviços para gestão de estoque e emissão de notas fiscais, integrando dois backends em **.NET C#** com um frontend em **Angular 19**.

#  Tecnologias Utilizadas*   **Frontend:** Angular 19, RxJS, HttpClient.*   **Backend:** .NET Core, Entity Framework Core.*   **Banco de Dados:** SQLite (Faturamento e Estoque).*   **Arquitetura:** Microsserviços com comunicação via HTTP.

# Como Executar o Projeto
Siga a ordem abaixo para garantir que a integração funcione corretamente:

# 1. Backend: Stock.API (Porta 5085)Navegue até a pasta `Stock.API` e execute:
``bash``
dotnet run

# 2. Backend: Billing.API (Porta 5102)
Navegue até a pasta Billing.API e execute:

dotnet run

# 3. Frontend: Angular (Porta 4200)
Navegue até a pasta Korp_Teste_Willian e execute:

npm install
ng serve

Acesse: http://localhost:4200
------------------------------
# 📝 Explicação Técnica (Requisitos do Teste)## Ciclos de Vida do Angular
Utilizei o hook ngOnInit no componente de faturamento para carregar automaticamente a lista de notas fiscais assim que a página é inicializada, garantindo que o usuário sempre veja os dados atualizados vindos do banco de dados.

# RxJS e Programação Reativa
A comunicação com os microsserviços foi feita utilizando Observables do RxJS através do HttpClient. Implementei o método .subscribe() para lidar com as respostas assíncronas, permitindo que a interface reaja em tempo real ao sucesso ou erro das operações (como atualizar a tabela imediatamente após salvar uma nota).

# Tratamento de Falhas e CORS
Configurei políticas de CORS nos backends para permitir a comunicação segura com o frontend. No Angular, utilizei blocos de error nos subscribers para fornecer feedbacks visuais (alertas) ao usuário caso um dos microsserviços esteja offline ou ocorra um erro de processamento.

## Integração entre Microsserviços
O fluxo de baixa de estoque ocorre de forma automática: ao emitir uma nota fiscal no Billing.API, o backend envia uma requisição POST para o endpoint baixar-estoque no Stock.API, garantindo a integridade dos dados entre os dois bancos de dados.
------------------------------
Desenvolvido por Willian Kelvin Ferreira de Assunção para o processo seletivo da Korp.


