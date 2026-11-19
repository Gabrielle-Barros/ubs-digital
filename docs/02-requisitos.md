# 02 — Requisitos do Sistema UBS Digital

## 1. Introdução

Este documento apresenta os requisitos funcionais e não funcionais da Prova de Conceito (POC) do UBS Digital.

Os requisitos foram definidos considerando as necessidades identificadas durante a atividade extensionista universitária e a proposta de desenvolvimento de uma solução para gerenciamento de agendamentos em Unidades Básicas de Saúde.

O sistema tem como finalidade facilitar o acesso dos cidadãos aos serviços de saúde, reduzir a burocracia nos processos de agendamento e melhorar a organização das atividades administrativas da unidade.

## 2. Atores do sistema

Os atores representam os usuários que interagem com a plataforma.

- **Cidadão:** realiza consultas de disponibilidade, efetua agendamentos, acompanha seus atendimentos e realiza cancelamentos conforme as regras estabelecidas.
- **Atendente:** administra agendas, horários e vagas, acompanha os agendamentos e gerencia ocorrências que possam comprometer os atendimentos programados.
- **Administrador:** gerencia usuários, serviços, profissionais e configurações gerais da unidade.

## 3. Requisitos funcionais (RF)

| Código | Descrição |
|---|---|
| RF01 | Permitir o cadastro de cidadãos. |
| RF02 | Permitir a autenticação dos usuários. |
| RF03 | Exibir os serviços disponíveis na UBS. |
| RF04 | Permitir a consulta de dias e horários disponíveis. |
| RF05 | Permitir que o cidadão realize e confirme automaticamente um agendamento. |
| RF06 | Validar a disponibilidade das vagas antes da confirmação do agendamento, respeitando os limites configurados. |
| RF07 | Permitir o cancelamento de agendamentos conforme as regras estabelecidas. |
| RF08 | Permitir que o cidadão consulte seus agendamentos e respectivos status. |
| RF09 | Permitir o gerenciamento de serviços, profissionais, dias de atendimento, horários e quantidade de vagas. |
| RF10 | Permitir a configuração de agendas exclusivas para públicos específicos, como gestantes. |
| RF11 | Disponibilizar painel administrativo com indicadores básicos de agendamentos. |
| RF12 | Apresentar uma pergunta inicial sobre gestação para direcionar a visualização das agendas disponíveis. |
| RF13 | Permitir o registro e gerenciamento de ocorrências que comprometam os atendimentos programados. |
| RF14 | Permitir a identificação dos agendamentos e cidadãos afetados por uma ocorrência. |
| RF15 | Permitir o envio de notificações aos cidadãos afetados, informando sobre imprevistos e a necessidade de reagendamento. |
| RF16 | Permitir que o cidadão realize um novo agendamento conforme a disponibilidade da agenda. |

## 4. Requisitos não funcionais (RNF)

| Código | Descrição |
|---|---|
| RNF01 | O sistema deverá proteger os dados pessoais dos usuários. |
| RNF02 | O sistema deverá respeitar os princípios e requisitos aplicáveis da Lei Geral de Proteção de Dados (LGPD). |
| RNF03 | A interface deverá ser responsiva e acessível. |
| RNF04 | O sistema deverá possuir controle de acesso baseado em perfis e permissões. |
| RNF05 | O sistema deverá evitar conflitos e duplicidade de agendamentos. |
| RNF06 | O sistema deverá manter registros de auditoria das operações relevantes. |
| RNF07 | A arquitetura deverá permitir futuras expansões para outras UBS. |
| RNF08 | O sistema deverá apresentar desempenho adequado às operações previstas na POC. |
| RNF09 | O sistema deverá garantir a integridade dos agendamentos em operações simultâneas, impedindo a ocupação duplicada de vagas e o ultrapassamento da capacidade configurada. |

## 5. Regras gerais de negócio

1. Cada unidade de saúde deverá possuir seus próprios serviços, dias de atendimento, horários e quantidade de vagas.

2. Todos os agendamentos previstos no escopo inicial serão realizados automaticamente pelo sistema, sem necessidade de aprovação individual da equipe.

3. A quantidade de vagas deverá ser configurável por serviço, dia e período de atendimento.

4. O sistema deverá respeitar os horários estabelecidos e impedir que a quantidade de agendamentos ultrapasse o limite de vagas configurado.

5. Quando todas as vagas de um serviço ou período estiverem ocupadas, o sistema deverá bloquear novos agendamentos e informar ao cidadão sobre a indisponibilidade.

6. A disponibilidade deverá ser validada novamente no momento da confirmação, evitando agendamentos duplicados ou acima da capacidade.

7. Agendamentos cancelados poderão liberar vagas para novas solicitações, conforme as regras da agenda.

8. A equipe da UBS poderá configurar dias e horários destinados exclusivamente a públicos específicos, como gestantes.

9. No início do acesso ao sistema, o cidadão deverá responder à pergunta sobre gestação, selecionando uma das opções: Sim ou Não.

10. A resposta fornecida será utilizada para direcionar a visualização das agendas, apresentando os horários exclusivos para gestantes ou os horários destinados ao público geral.

11. O sistema não deverá utilizar o sexo cadastrado como critério automático para bloquear o acesso às agendas exclusivas para gestantes.

12. A informação sobre gestação deverá ser tratada como dado pessoal sensível, observando a LGPD, com finalidade definida, coleta mínima, acesso restrito e avaliação da necessidade de armazenamento.

13. A equipe da UBS poderá registrar ocorrências operacionais que comprometam a realização dos atendimentos programados.

14. Quando uma ocorrência afetar agendamentos existentes, a equipe poderá identificar os cidadãos impactados e enviar notificações informativas.

15. As notificações deverão informar sobre o imprevisto e orientar o cidadão quanto à necessidade de realizar um novo agendamento.

16. O novo agendamento deverá respeitar a disponibilidade de vagas e horários existentes.

17. O sistema deverá respeitar os perfis de acesso e as permissões de cada usuário.

## 6. Critérios de aceitação

A POC será considerada funcional quando permitir:

- Cadastro e autenticação de cidadãos.
- Consulta aos serviços disponíveis na UBS.
- Configuração de dias, horários e quantidade de vagas por serviço e período.
- Direcionamento das agendas conforme a resposta inicial sobre gestação.
- Visualização de agendas exclusivas para gestantes e agendas destinadas ao público geral.
- Realização e confirmação automática de agendamentos.
- Atualização da disponibilidade após operações de agendamento e cancelamento.
- Bloqueio de novos agendamentos quando não houver vagas disponíveis.
- Prevenção de agendamentos duplicados, inclusive em operações simultâneas.
- Consulta e cancelamento de agendamentos.
- Registro e gerenciamento de ocorrências operacionais.
- Identificação dos cidadãos afetados por ocorrências.
- Envio de notificações aos cidadãos impactados.
- Possibilidade de realização de novo agendamento após a comunicação do imprevisto.

## 7. Limites da POC

A primeira versão do UBS Digital não contemplará:

- Prontuário eletrônico.
- Armazenamento de histórico clínico.
- Emissão de receitas médicas.
- Telemedicina.
- Integração com sistemas nacionais do SUS.

O desenvolvimento utilizará dados fictícios para testes, sem exposição de informações pessoais ou sensíveis coletadas durante a atividade extensionista.

A POC terá como foco o gerenciamento de agendamentos, a organização das agendas, o controle de vagas e a comunicação de ocorrências operacionais.
