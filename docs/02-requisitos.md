# 02 — Requisitos do Sistema UBS Digital

## 1. Introdução

Este documento apresenta os requisitos funcionais e não funcionais da Prova de Conceito (POC) do UBS Digital.

Os requisitos foram definidos considerando as necessidades identificadas durante a atividade extensionista universitária e a proposta de desenvolvimento de uma solução para gerenciamento de agendamentos em Unidades Básicas de Saúde.

## 2. Atores do sistema

Os atores representam os usuários que interagem com a plataforma.

- **Cidadão:** realiza consultas de disponibilidade, solicita agendamentos e acompanha seus atendimentos.
- **Atendente:** gerencia solicitações, aprova ou rejeita agendamentos e administra horários.
- **Administrador:** gerencia usuários, serviços e configurações da unidade.

## 3. Requisitos funcionais (RF)

| Código | Descrição |
|---|---|
| RF01 | Permitir cadastro de cidadãos. |
| RF02 | Permitir autenticação de usuários. |
| RF03 | Exibir os serviços disponíveis na UBS. |
| RF04 | Consultar horários disponíveis. |
| RF05 | Permitir solicitação de agendamentos. |
| RF06 | Confirmar automaticamente agendamentos configurados para esse modo. |
| RF07 | Permitir aprovação ou rejeição de solicitações pela equipe da UBS. |
| RF08 | Permitir cancelamento de agendamentos. |
| RF09 | Permitir consulta ao histórico e ao status dos agendamentos. |
| RF10 | Permitir gerenciamento de serviços, profissionais e horários. |
| RF11 | Disponibilizar painel administrativo com indicadores básicos. |

## 4. Requisitos não funcionais (RNF)

| Código | Descrição |
|---|---|
| RNF01 | O sistema deverá proteger os dados dos usuários. |
| RNF02 | O sistema deverá respeitar os princípios e requisitos aplicáveis da LGPD. |
| RNF03 | A interface deverá ser responsiva e acessível. |
| RNF04 | O sistema deverá possuir controle de acesso baseado em perfis. |
| RNF05 | O sistema deverá evitar conflitos e duplicidade de agendamentos. |
| RNF06 | O sistema deverá manter registros de auditoria das operações relevantes. |
| RNF07 | A arquitetura deverá permitir futuras expansões para outras UBS. |
| RNF08 | O sistema deverá apresentar desempenho adequado às operações previstas na POC. |

## 5. Regras gerais de negócio

- Cada unidade deverá possuir seus próprios serviços e horários.
- Um horário não poderá ser ocupado por agendamentos ativos incompatíveis.
- Serviços configurados para agendamento automático terão confirmação após validação da disponibilidade.
- Solicitações sujeitas à aprovação permanecerão pendentes até análise da equipe.
- A aprovação deverá verificar novamente a disponibilidade do horário.
- Solicitações pendentes poderão possuir prazo de expiração, com liberação do horário após o vencimento.
- O acesso às funcionalidades deverá respeitar o perfil de cada usuário.

## 6. Critérios de aceitação

A POC será considerada funcional quando permitir:

- Cadastro e autenticação de cidadãos.
- Consulta aos serviços e horários disponíveis.
- Realização de agendamentos automáticos.
- Solicitação de agendamentos sujeitos à aprovação.
- Aprovação e rejeição pela equipe da UBS.
- Atualização da disponibilidade após operações de agendamento.
- Consulta e cancelamento de agendamentos.
- Prevenção de agendamentos duplicados.

## 7. Limites da POC

A primeira versão não contemplará prontuário eletrônico, armazenamento de histórico clínico, emissão de receitas, telemedicina ou integração com sistemas nacionais do SUS.

O desenvolvimento utilizará dados fictícios para testes, sem exposição de informações pessoais ou sensíveis coletadas durante a atividade extensionista.
