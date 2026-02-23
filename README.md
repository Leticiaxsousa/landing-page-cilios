#  Lash Design - Landing Page & Sistema de Agendamento Online

Este projeto supervisionado consiste no desenvolvimento de uma aplicação web completa (Landing Page + Sistema de Gestão) para profissionais de design de cílios. O objetivo é unir a divulgação do portfólio profissional com a automação de agendamentos.

##  1. Visão Geral
O sistema funciona como o cartão de visitas digital da profissional. Ele combina uma **Landing Page** de alta conversão para exibir o trabalho e educar a cliente, com um motor de agendamentos em tempo real que elimina a necessidade de marcações manuais.

##  2. O Problema
Agendamentos manuais via chat frequentemente causam:
* Conflitos de horários e esquecimento de clientes.
* Perda de tempo explicando cuidados básicos repetidas vezes.
* Falta de um portfólio profissional organizado para novos clientes.

## 3. Objetivo Geral
Desenvolver uma plataforma onde a cliente possa conhecer o trabalho, aprender sobre os cuidados necessários, agendar seu serviço de forma autônoma e receber confirmações automáticas via **WhatsApp**.

---

## 4. Perfis de Usuário e Funcionalidades

###  Experiência da Cliente (Landing Page)
* **Portfólio:** Visualização do trabalho e biografia da profissional.
* **Catálogo de Serviços:** Lista detalhada com tipos de procedimentos, preços e durações.
* **Central de Cuidados:** Seção dedicada com dicas de manutenção e higiene dos cílios (Pós-procedimento).
* **Agendamento Inteligente:** Consulta de horários reais e reserva instantânea.
* **Notificação:** Recebimento de confirmação automática dos dados do agendamento via WhatsApp.

### Painel da Administradora (Lash Designer)
* **Acesso Restrito:** Login seguro via Firebase Authentication.
* **Gestão de Conteúdo:** Cadastrar, editar e remover serviços oferecidos.
* **Controle de Agenda:** Definição de horários de atendimento, bloqueios de datas e gestão de locais/unidades.
* **Monitoramento:** Visualização clara de todos os agendamentos realizados com opção de cancelamento.

---

##  5. Tecnologias Utilizadas
* **Frontend:** HTML5, CSS3 (Design Responsivo/Mobile-First) e JavaScript (ES6+).
* **Backend & DB:** Firebase Firestore (Banco de dados NoSQL em tempo real).
* **Autenticação:** Firebase Authentication.
* **Integrações:** API do WhatsApp (Link direto/Mensagens estruturadas).
* **Versionamento:** GitHub (Acompanhamento semanal da evolução).

##  6. Requisitos Principais
* [x] **Segurança:** Bloqueio de agendamentos duplicados no mesmo horário.
* [x] **Performance:** Carregamento otimizado para navegação mobile.
* [x] **UX (User Experience):** Seção de dicas interativa para educar a cliente.
* [x] **Cloud:** Armazenamento de dados persistente na nuvem.

##  7. Escopo Não Contemplado (Out of Scope)
* Pagamentos online (Gateway direto no site).
* Chat interno em tempo real entre admin e cliente.
* Múltiplos níveis de permissão (apenas um administrador).

---

##  8. Estrutura de Dados (Visão Lógica)
| Entidade | Responsabilidade |
| :--- | :--- |
| **Administradora** | Controla o fluxo da agenda e os serviços ativos. |
| **Cliente** | Visualiza conteúdos, dicas e realiza a reserva. |
| **Serviço** | Define a categoria (Fio a Fio, Volume Russo, etc), valor e tempo. |
| **Agendamento** | Registro único vinculando data, hora, cliente e unidade. |
| **Dicas/Cuidados** | Conteúdo educativo exibido na Landing Page. |

---
## Diagrama de Fluxo do Sistema

```mermaid
graph TD
    A[Cliente] -->|Acessa| B[Landing Page]
    B --> C{Deseja Agendar?}
    C -->|Sim| D[Escolhe Serviço e Horário]
    D --> E[Agendamento registrado no Banco de Dados]
    E --> F[Confirmação via WhatsApp]
    C -->|Não| G[Lê Dicas de Cuidados]

    Admin[Administradora] -->|Faz Login| H[Painel de Controle]
    H --> I[Gerencia Agenda]
    H --> J[Gerencia Serviços]
