# Fluxos de Agendamento

## 1. Objetivo

Documentar os fluxos de funcionamento do processo de agendamento do UBS Digital, descrevendo as etapas, decisões e validações necessárias para garantir a organização e a integridade das vagas disponíveis.

## 2. Fluxo de Agendamento Automático

O agendamento automático permite que o cidadão selecione um serviço e um horário disponível, recebendo a confirmação após a validação das regras de disponibilidade.

### 2.1. Etapas do processo

1. O cidadão acessa o UBS Digital.
2. Seleciona a Unidade Básica de Saúde (UBS).
3. Escolhe o serviço desejado.
4. Consulta os horários disponíveis.
5. O sistema verifica se existem vagas disponíveis.
6. Caso não existam vagas, o sistema informa a indisponibilidade e encerra o processo.
7. Caso existam vagas, o cidadão seleciona um horário.
8. O sistema realiza uma nova validação da disponibilidade.
9. Se a vaga continuar disponível, o sistema registra e confirma o agendamento.
10. Se a vaga não estiver mais disponível, o sistema informa a indisponibilidade e não permite a confirmação.

### 2.2. Regras e validações

- O agendamento deverá respeitar a quantidade de vagas configurada para cada serviço e período.
- O sistema não poderá ultrapassar o limite de vagas estabelecido.
- A disponibilidade deverá ser validada novamente no momento da confirmação.
- O banco de dados deverá garantir que uma mesma vaga não seja ocupada por mais de um agendamento ativo.
- Quando não houver disponibilidade, o cidadão deverá receber uma mensagem informativa.

### 2.3. Controle de concorrência

O sistema deverá implementar mecanismos de controle de concorrência para evitar que dois cidadãos ocupem simultaneamente a mesma vaga.

A validação deverá ocorrer no backend e ser protegida por mecanismos de integridade no banco de dados, evitando que solicitações simultâneas resultem em agendamentos duplicados.
