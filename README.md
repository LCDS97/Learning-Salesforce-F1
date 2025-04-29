Projeto Salesforce: Gerenciamento de Patrocínios

📦 Visão Geral

Este projeto simula um ambiente Salesforce voltado ao gerenciamento de patrocínios esportivos, utilizando Account (como Patrocinador), Contact (como Piloto), Opportunity (como oportunidades de patrocínio) e o objeto personalizado Patrocinio.

Seu principal objetivo é modelar regras de negócio complexas, integrações, automações e componentes reutilizáveis dentro de uma org de desenvolvedor, com versionamento e colaboração no GitHub, simulando um pipeline DevOps manual.

🗂 Estrutura do Projeto por Tópico

📘 Objetos e Campos

Objetos Utilizados:

Account: Patrocinador

Contact: Piloto

Opportunity: Oportunidade de Patrocínio

Patrocinio (Custom Object)

Campos Personalizados e Fórmulas:

Account

Campo de picklist: Setor do Patrocinador

Fórmula: Valor Disponível (relacionado às oportunidades e patrocínios)

Contact

Campo de picklist: País do Piloto

Fórmula: Idade (a partir da data de nascimento)

Patrocinio

Valor do patrocínio

Opportunity

Campo de validação: Valor maior que disponível

🔐 Validações e Regras de Negócio

Piloto ativo deve estar vinculado a uma equipe

Piloto inativo não pode estar vinculado a patrocínio

E-mail duplicado para contatos do tipo piloto

Oportunidade maior que valor disponível

Valor total menor que valor patrocinado

Impedir criação de patrocínio se a oportunidade não estiver fechada e ganha

Valor de patrocínio maior que valor da oportunidade

Validação de CPF duplicado via Apex

Data de fechamento inválida (validation rule)

⚙️ Automação (Flows, Apex e Processos)

Flows:

Flow Trigger: Atualização automática de status em oportunidades

Screen Flow: Onboarding de nova conta

Flow: Envio automático de e-mail ao criar novo contato

Apex:

Envio de e-mail com informações customizadas

Batch de inativação de patrocínios antigos

Trigger: Impedir que piloto já patrocinado receba novo patrocínio

Quick Actions:

Comprovante de patrocínios

Tela de divisão de patrocínio

Ação Admin de reatribuição em massa de contas

📊 Relatórios e Dashboards

Relatórios por status, valor e data dos patrocínios

Painel de visualização para patrocinadores

🧩 Componentes LWC

LWC: Exibição dinâmica de Permission Set Groups por campo (funcionalidade avulsa, não é o projeto em si)

LWC: Pilotos Ativos (disponibilizado na Home Page)

🧱 UI e Layout

Criação de guias personalizadas

Criação de aplicativo personalizado

Customização de layouts de página Lightning por objeto

Atribuição de Lightning Pages

🔁 Integrações

Integração com API pública da Fórmula 1 (consulta de dados externos)

🧪 Testes

Cada classe e trigger terá cobertura de teste em suas respectivas classes

Seção de testes será completada conforme as classes forem adicionadas

🔲 [Reservado para Classes de Teste]

🚀 Versionamento Manual (Simulando DevOps Center)

📁 Estrutura Recomendada no GitHub

├── force-app/
│   ├── main/
│   │   ├── default/
│   │   │   ├── classes/
│   │   │   ├── lwc/
│   │   │   ├── objects/
│   │   │   ├── flows/
│   │   │   ├── layouts/
│   │   │   ├── permissionsets/
│   │   │   ├── tabs/
│   │   │   ├── applications/
│   │   │   ├── staticresources/

👥 Controle de Permissões e Colaboração no GitHub

Criar repositório e adicionar colaborador (Settings > Collaborators)

Habilitar branch protection na branch main:

Exigir aprovação de Pull Requests

Exigir revisão obrigatória do dono (ex: lucas.cds1997@gmail.com)

🔄 Ciclo Manual Simulado:

Desenvolvedor faz alterações na org de Dev

Executa sfdx force:source:pull para trazer alterações locais

Cria uma branch e faz commit: feat/validacao-email-piloto

Push para GitHub e abre Pull Request

Owner aprova ou solicita mudanças

PR aprovado = merge na main

📈 Modelo de Dados

Account (Patrocinador)

Nome, Setor, Valor Disponível (fórmula)

Contact (Piloto)

Nome, País, Idade (fórmula), Email

Opportunity

Valor, Status, Data Fechamento, Relacionamento com Patrocínio

Patrocinio (Custom Object)

Valor, Conta relacionada, Piloto, Status

📅 Planejamento Futuro

Substituir trigger de CPF duplicado por validação com Flow

Publicar base de conhecimento do projeto

Criação de classes reutilizáveis para validações genéricas

Painel dinâmico de indicadores para patrocinadores

Criação de documentação técnica HTML com Storybook para os LWC criados

🔗 Referências Úteis

Developer Guide - Salesforce

Salesforce Metadata Coverage

SFDX CLI Commands

VSCode + Salesforce Extension Pack

📌 Projeto mantido por Lucas (lucas.cds1997@gmail.com)

👥 Contribuidor: Nathan (nathannunessp587@gmail.com)

