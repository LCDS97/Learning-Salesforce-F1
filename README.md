# Projeto Salesforce - Gestão de Patrocínios para Pilotos de Corrida

## Visão Geral
Este projeto simula a implementação de uma solução Salesforce para gerenciar patrocinadores, pilotos, oportunidades de patrocínio e processos relacionados, com foco em funcionalidades relevantes para aprendizado da Plataforma.

A solução utiliza objetos padrão como Account, Contact e Opportunity, além de objetos personalizados como Patrocinio.

## Estrutura do Projeto
### Objetos Utilizados
- **Account**: representa o patrocinador
- **Contact**: representa o piloto
- **Opportunity**: representa uma oportunidade de patrocínio
- **Patrocinio (Custom Object)**: liga uma oportunidade aprovada a um piloto

### Campos Personalizados e Fórmulas
- Campos personalizados nos objetos Account, Contact, Opportunity e Patrocinio
- Fórmula de **idade** no Contact
- Fórmula de **valor disponível** na Account

### Picklists Personalizadas
- **Ramo de atuação** (Account)
- **Setor do patrocinador** (Account)
- **País do piloto** (Contact)

## Funcionalidades Desenvolvidas

### Componentes Lightning (LWC)
- Componente de **Permission Set** (funcionalidade para gestão de permissões)
- **Componente de pilotos ativos**
- Disponibilização do componente na Home

### Experiência do Usuário
- Criação de **Guias** e **Aplicativo Personalizado**
- **Layouts e Lightning Pages** por perfil/objeto
- **Quick Action**: Comprovante de Patrocínio
- **Tela de divisão de patrocínio**

### Lógicas e Regras de Negócio
#### Validation Rules
- Piloto ativo sem equipe
- Piloto inativo não pode receber patrocínio
- E-mail duplicado para piloto
- Valor da oportunidade maior que valor disponível
- Valor total de patrocínio menor que o valor na oportunidade
- Oportunidade marcada como "Fechada e Perdida"
- Criação de patrocínio sem oportunidade "Fechada e Ganha"
- Valor do patrocínio maior que o valor da oportunidade
- Data de fechamento inválida na oportunidade

#### Apex
- Trigger: impedir que um piloto já patrocinado receba novo patrocínio
- Classe de envio de e-mail com informações customizadas
- Validação de CPF duplicado via Apex
- **Classes de Teste** para cada classe (reservar espaço aqui para inserir depois)

#### Automação
- Flow Trigger: atualização automática do status da oportunidade
- Screen Flow: onboarding de nova conta
- Flow: envio automático de e-mail ao criar um novo contato
- Ação administrativa: reatribuição em massa de contas
- Processo de aprovação da oportunidade com notificação de aprovação

#### Batch Apex
- Inativação de patrocínios antigos

### Integrações
- Integração com API pública da Fórmula 1 (exibição de dados em tela ou armazenamento em objeto customizado)

## Simulação Manual de DevOps

Como DevOps Center não será utilizado, o processo de versionamento será feito de forma **manual** com uso de GitHub, seguindo os passos abaixo:

### Processo Manual
1. Desenvolvimento local na Org com Scratch Org ou Sandbox
2. Commit de alterações locais via SFDX:
   ```bash
   git add .
   git commit -m "feat: adiciona fluxo de onboarding de conta"
   git push origin main
   ```
3. Controle de permissões com **Permission Sets**
4. Controle de versões de metadata somente com arquivos relevantes, **sem versionamento do metadata completo**

## Modelo de Dados

### Objetos e Relacionamentos
- **Account (Patrocinador)** - padrão
- **Contact (Piloto)** - padrão
- **Opportunity (Oportunidade de Patrocínio)** - padrão
- **Patrocinio** (custom object)
  - Lookup para Piloto
  - Lookup para Oportunidade

## Planejamento Futuro
- Adicionar permissionamento por perfil e permission set group
- Criar testes automatizados para flows e validações
- Melhorar UX com Dynamic Forms e Visibility Rules
- Expandir integração com outras APIs esportivas
- Criar painel executivo de análise de desempenho

## Referências Úteis
- [Trailhead - Lightning App Builder](https://trailhead.salesforce.com/en/content/learn/modules/lightning-app-builder)
- [Trailhead - Apex Testing](https://trailhead.salesforce.com/en/content/learn/modules/apex_testing)
- [Salesforce Dev Docs](https://developer.salesforce.com/docs)
- [API Pública F1](https://ergast.com/mrd/)

