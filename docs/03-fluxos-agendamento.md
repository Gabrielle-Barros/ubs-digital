# Fluxos de Agendamento

## 1. Objetivo

Documentar os fluxos de funcionamento do UBS Digital, descrevendo as etapas, decisões e validações necessárias para organizar os agendamentos, controlar a disponibilidade de vagas e administrar situações que possam comprometer a realização dos atendimentos.

## 2. Direcionamento das Agendas

O sistema deverá realizar uma identificação inicial do cidadão para direcionar a visualização das agendas, considerando a existência de dias e horários destinados exclusivamente a públicos específicos, como gestantes.

### 2.1. Identificação inicial do cidadão

No início do acesso ao sistema, o cidadão deverá responder à pergunta:

**"Você está gestante?"**

As opções de resposta serão:

- Sim.
- Não.

A resposta será utilizada para direcionar a visualização das agendas disponíveis.

### 2.2. Regras de direcionamento

- Quando a resposta for "Sim", o sistema deverá apresentar as agendas destinadas às gestantes, conforme os serviços, dias e horários configurados pela UBS.
- Quando a resposta for "Não", o sistema deverá apresentar as agendas destinadas ao público geral, ocultando os horários exclusivos para gestantes.
- A equipe da UBS será responsável por configurar os dias, horários e quantidade de vagas destinados exclusivamente a esse público.
- A configuração poderá contemplar diferentes serviços, como pré-natal e atendimento odontológico.
- O direcionamento deverá ocorrer automaticamente, sem necessidade de aprovação prévia individual pela equipe da UBS.
- A resposta deverá ser tratada como dado pessoal sensível, observando os requisitos da LGPD, com coleta mínima, finalidade definida e acesso restrito.
- O sistema não deverá utilizar o sexo cadastrado como critério automático para bloquear o acesso às agendas exclusivas para gestantes.

## 3. Fluxo de Agendamento Automático

O agendamento automático permite que o cidadão selecione um serviço e um horário disponível, recebendo a confirmação após a validação das regras de disponibilidade.

Todos os serviços contemplados no escopo inicial utilizarão o agendamento automático, sem necessidade de aprovação individual por parte dos atendentes.

### 3.1. Etapas do processo

1. O cidadão acessa o UBS Digital.
2. Responde à pergunta inicial sobre gestação.
3. O sistema direciona a visualização das agendas conforme a resposta.
4. O cidadão seleciona a Unidade Básica de Saúde (UBS).
5. Escolhe o serviço desejado.
6. Consulta os dias e horários disponíveis.
7. O sistema verifica se existem vagas disponíveis.
8. Caso não existam vagas, o sistema informa a indisponibilidade e encerra o processo.
9. Caso existam vagas, o cidadão seleciona um horário.
10. O sistema realiza uma nova validação da disponibilidade.
11. Se a vaga continuar disponível, o sistema registra e confirma automaticamente o agendamento.
12. Se a vaga não estiver mais disponível, o sistema informa a indisponibilidade e não permite a confirmação.

### 3.2. Regras e validações

- O agendamento deverá respeitar a quantidade de vagas configurada para cada serviço, dia e período de atendimento.
- Os horários disponíveis deverão ser previamente cadastrados pela equipe da UBS.
- O sistema não poderá ultrapassar o limite de vagas estabelecido.
- A disponibilidade deverá ser validada novamente no momento da confirmação.
- O banco de dados deverá garantir que uma mesma vaga não seja ocupada por mais de um agendamento ativo.
- Quando todas as vagas estiverem ocupadas, o sistema deverá bloquear novos agendamentos e informar ao cidadão sobre a indisponibilidade.
- Agendamentos cancelados poderão liberar vagas para novas solicitações, conforme as regras estabelecidas.
- A confirmação do agendamento deverá ocorrer automaticamente, sem necessidade de aprovação individual da equipe.

### 3.3. Controle de concorrência

O sistema deverá implementar mecanismos de controle de concorrência para evitar que dois cidadãos ocupem simultaneamente a mesma vaga.

A validação deverá ocorrer no backend e ser protegida por mecanismos de integridade no banco de dados, evitando que solicitações simultâneas resultem em agendamentos duplicados ou ultrapassem a quantidade de vagas configurada.

## 4. Fluxo de Tratamento de Ocorrências

O sistema deverá permitir que a equipe da UBS gerencie situações imprevistas que comprometam a realização dos atendimentos previamente agendados, possibilitando a identificação dos cidadãos afetados e o envio de notificações para orientar o reagendamento.

### 4.1. Objetivo

Disponibilizar ferramentas administrativas para que os agentes da UBS possam comunicar alterações e imprevistos que impossibilitem a realização dos atendimentos programados, reduzindo transtornos para os cidadãos e melhorando a organização da unidade.

### 4.2. Etapas do processo

1. Ocorre um imprevisto que impossibilita a realização de determinados atendimentos.
2. O agente acessa o painel administrativo do UBS Digital.
3. Registra a ocorrência e informa os dados necessários.
4. Identifica os agendamentos afetados pela ocorrência.
5. Seleciona os cidadãos que deverão receber a comunicação.
6. O sistema envia uma notificação informando sobre o imprevisto e a necessidade de reagendamento.
7. O cidadão recebe a comunicação e acessa o UBS Digital.
8. Consulta os horários disponíveis.
9. Realiza um novo agendamento conforme a disponibilidade existente.

### 4.3. Exemplos de ocorrências

- Ausência do médico ou de outro profissional responsável pelo atendimento.
- Falta de energia elétrica.
- Falta de abastecimento de água.
- Problemas estruturais na unidade.
- Outros imprevistos operacionais que impeçam a realização dos atendimentos programados.

### 4.4. Regras do processo

- A equipe deverá conseguir identificar os agendamentos afetados por uma ocorrência.
- As notificações deverão ser direcionadas somente aos cidadãos impactados.
- A comunicação deverá informar claramente o motivo da alteração e a necessidade de reagendamento.
- O sistema deverá permitir o registro administrativo das ocorrências e das comunicações realizadas.
- O novo agendamento deverá respeitar a disponibilidade de vagas e horários existentes.
- A equipe deverá ter acesso às funcionalidades de gerenciamento de ocorrências conforme seu perfil de acesso.
- O sistema deverá preservar o histórico dos agendamentos afetados e das ações administrativas realizadas.
