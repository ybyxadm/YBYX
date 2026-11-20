
# Vetinos — PLANO DE DESENVOLVIMENTO

Documento oficial de planejamento, prioridades, arquitetura e evolução do Vetinos.

**Repositório:** 

Repositórios em : https://github.com/ybyxadm
site institucional git: https://ybyxadm.github.io/web.vetinos/
site sistema git: https://ybyxadm.github.io/web.vetinos/

redirecionamentos
Site institucional firebase: https://web-vetinos.web.app
      https://web-vetinos.firebaseapp.com
site sistema firebase: https://app-vetinos.web.app
      https://app-vetinos.firebaseapp.com

> Este documento descreve o planejamento do sistema. Uma funcionalidade somente poderá ser considerada implementada ou validada após verificação do código e execução dos testes correspondentes.

---

# 1. VISÃO DO PROJETO

O Vetinos é uma plataforma de gestão veterinária destinada a clínicas, hospitais e redes veterinárias.

O sistema deverá permitir que uma organização possua uma ou várias unidades, com cadastros compartilhados e operações independentes conforme as permissões estabelecidas.

Princípios:

- Evoluir.
- Integrar.
- Proteger.

## 1.1 Objetivos

- Construir uma plataforma veterinária modular.
- Permitir crescimento de uma clínica para uma rede.
- Compartilhar cadastros dentro da organização.
- Manter isolamento entre organizações.
- Permitir gestão independente das unidades.
- Disponibilizar módulos gradualmente.
- Garantir integridade e segurança dos dados.
- Preparar a arquitetura para futuras expansões.

# 2. AMBIENTES DO SISTEMA

Serão utilizados três ambientes independentes.

| Nome | Identificação técnica | Utilização |
|---|---|---|
| DESENVOLVIMENTO | DEV | Construção e correção |
| TESTES | HML | Validação e simulações |
| OFICIAL | PRD | Operação real |

## 2.1 DESENVOLVIMENTO

Ambiente utilizado durante a programação.

Objetivos:

- Criar funcionalidades.
- Corrigir erros.
- Testar componentes.
- Realizar alterações estruturais.
- Validar integrações iniciais.

## 2.2 TESTES

Ambiente destinado à validação antes da liberação oficial.

Objetivos:

- Testar fluxos completos.
- Simular falhas de comunicação.
- Testar indisponibilidade do banco.
- Verificar mensagens de erro.
- Validar permissões.
- Testar isolamento entre organizações.
- Verificar comportamento dos módulos integrados.

Deverá utilizar dados fictícios ou devidamente preparados para testes.

Não utilizar dados clínicos reais sem autorização, controles de segurança e política adequada.

## 2.3 OFICIAL

Ambiente destinado à utilização real pelas organizações contratantes.

Regras:

- Não realizar testes destrutivos.
- Não provocar esgotamento de cotas.
- Não desativar serviços para simular falhas.
- Não publicar alterações sem validação e autorização.
- Manter monitoramento, backup e segurança.

## 2.4 Estrutura técnica

O projeto deverá manter:

- Um único código-fonte.
- Um único projeto local no VS Code.
- Um único repositório GitHub.
- Projetos Firebase independentes para cada ambiente.
- Configurações e variáveis de ambiente específicas.

Sugestão de identificação visual dos projetos Firebase:

- Vetinos - DESENVOLVIMENTO
- Vetinos - TESTES
- Vetinos - OFICIAL

A implementação deverá verificar a configuração atual antes de criar, migrar ou renomear projetos.

Arquivos de ambiente, quando adotados, deverão utilizar a convenção adequada ao Vite, por exemplo:

- `.env.development`
- `.env.staging`
- `.env.production`

Credenciais e configurações privadas não deverão ser publicadas no repositório.

# 3. ARQUITETURA MULTIEMPRESA E MULTIUNIDADE

## 3.1 Organização

Representa o cliente contratante do Vetinos.

Pode ser:

- Clínica independente.
- Hospital veterinário.
- Rede veterinária.

Cada organização deverá possuir identificação única.

Os dados de uma organização não poderão ser acessados por outra.

## 3.2 Unidades

Uma organização poderá possuir uma ou várias unidades.

Cada unidade deverá possuir:

- Identificação própria.
- Dados administrativos.
- Colaboradores autorizados.
- Estoque independente.
- Financeiro independente.
- Operação própria.

Gestores autorizados poderão consultar informações consolidadas.

## 3.3 Usuários

Os usuários deverão possuir vínculos e permissões definidos.

O sistema deverá permitir:

- Cadastro centralizado.
- Vínculo à organização.
- Acesso a uma ou mais unidades.
- Permissões por módulo.
- Ativação e desativação.
- Registro de ações relevantes.

## 3.4 Tutores e pacientes

Tutores e pacientes pertencerão à organização.

Não deverão ser duplicados quando o mesmo paciente for atendido em unidades diferentes da mesma organização.

O acesso deverá respeitar as permissões do usuário e as regras de compartilhamento clínico.

# 4. ORDEM DE IMPLEMENTAÇÃO

A ordem abaixo estabelece dependências técnicas. A liberação de cada etapa dependerá da implementação e validação.

## ETAPA 1 — FUNDAÇÃO DO SISTEMA

### 1.1 Organização

- [ ] Definir modelo de organização.
- [ ] Criar identificador único.
- [ ] Definir estrutura de dados.
- [ ] Definir vínculo com usuários.
- [ ] Definir estrutura de unidades.
- [ ] Implementar isolamento entre organizações.
- [ ] Criar testes com organizações fictícias.

### 1.2 Unidades

- [ ] Criar cadastro de unidades.
- [ ] Vincular unidades à organização.
- [ ] Definir unidade ativa.
- [ ] Definir permissões por unidade.
- [ ] Preparar consultas consolidadas.
- [ ] Testar separação de operações.

### 1.3 Usuários e permissões

- [ ] Revisar autenticação.
- [ ] Definir perfis.
- [ ] Definir permissões por módulo.
- [ ] Definir permissões por unidade.
- [ ] Proteger operações administrativas.
- [ ] Registrar ações relevantes.
- [ ] Testar acesso indevido.

**Critério de conclusão:** organizações e unidades isoladas, usuários vinculados corretamente e permissões validadas.

## ETAPA 2 — CADASTROS CENTRAIS

### 2.1 Tutores

- [ ] Cadastro de tutores.
- [ ] Nome e identificação.
- [ ] Telefone.
- [ ] E-mail.
- [ ] Endereço.
- [ ] Observações.
- [ ] Pesquisa.
- [ ] Edição.
- [ ] Controle de duplicidade.
- [ ] Vínculo à organização.

### 2.2 Pacientes

- [ ] Cadastro de cães.
- [ ] Cadastro de gatos.
- [ ] Cadastro de outras espécies.
- [ ] Nome.
- [ ] Espécie.
- [ ] Raça.
- [ ] Sexo.
- [ ] Data de nascimento ou idade estimada.
- [ ] Peso.
- [ ] Características.
- [ ] Foto, quando aplicável.
- [ ] Vínculo ao tutor.
- [ ] Histórico.
- [ ] Pesquisa e edição.

**Critério de conclusão:** tutor e paciente cadastrados uma única vez na organização, com vínculo consistente e acesso controlado.

## ETAPA 3 — ATENDIMENTO

<badge>PRIORIDADE PRINCIPAL</badge>

O atendimento será a primeira grande entrega operacional.

### 3.1 Consulta

- [ ] Selecionar tutor.
- [ ] Selecionar paciente.
- [ ] Registrar data e horário.
- [ ] Identificar profissional responsável.
- [ ] Registrar motivo da consulta.
- [ ] Criar atendimento.
- [ ] Consultar histórico do paciente.

### 3.2 Anamnese

- [ ] Registrar queixa principal.
- [ ] Registrar histórico.
- [ ] Registrar alimentação.
- [ ] Registrar vacinação.
- [ ] Registrar medicações em uso.
- [ ] Registrar informações relevantes.
- [ ] Registrar exame físico.
- [ ] Registrar sinais vitais.
- [ ] Registrar avaliação clínica.
- [ ] Registrar diagnóstico.
- [ ] Registrar conduta.

### 3.3 Receita veterinária

- [ ] Criar receita vinculada ao atendimento.
- [ ] Identificar paciente e tutor.
- [ ] Identificar profissional responsável.
- [ ] Registrar medicamentos e prescrições.
- [ ] Registrar orientações.
- [ ] Gerar documento PDF.
- [ ] Conferir apresentação e legibilidade.
- [ ] Validar impressão.
- [ ] Validar exportação.

A emissão deverá respeitar os requisitos legais aplicáveis e os dados profissionais necessários.

### 3.4 Lançamento de serviços

- [ ] Selecionar serviço.
- [ ] Registrar valor.
- [ ] Vincular ao atendimento.
- [ ] Identificar unidade.
- [ ] Identificar responsável.
- [ ] Disponibilizar informação para integração financeira.

### 3.5 Histórico clínico

- [ ] Consultar atendimentos anteriores.
- [ ] Consultar receitas.
- [ ] Consultar procedimentos.
- [ ] Consultar exames anexados.
- [ ] Identificar profissional responsável.
- [ ] Preservar histórico e rastreabilidade.

**Critério de conclusão:** fluxo completo de atendimento validado, incluindo consulta, anamnese, receita PDF e lançamento de serviço.

# 5. INTEGRAÇÃO DOS MÓDULOS

A integração deverá ser planejada desde a fundação.

Os módulos não poderão criar cadastros independentes de tutores e pacientes.

Exemplos:

| Módulo | Integração necessária |
|---|---|
| Atendimento | Utiliza organização, unidade, tutor e paciente |
| Internamento | Utiliza o mesmo paciente e histórico clínico |
| Vacinação | Utiliza paciente, tutor e histórico |
| Estoque | Fornece produtos e medicamentos conforme unidade |
| Calculadora de Doses | Utiliza paciente e peso atualizado, prescrição informada e dados de concentração/apresentação dos medicamentos; integra-se ao cadastro de medicamentos, atendimento, prontuário e internamento |
| Financeiro | Recebe serviços e cobranças dos atendimentos |
| Relatórios | Consolida dados conforme permissões |
| Treinamento de funcionários | Utiliza usuários, funções, permissões e unidades para atribuir trilhas e acompanhar capacitações |
| Assinatura eletrônica/digital | Integra documentos a tutores, pacientes, atendimentos, internações e procedimentos, mantendo evidências e rastreabilidade |
| Monitoramento de transfusão | Integra o paciente e o internamento ao registro de hemocomponentes, parâmetros e intercorrências |
| Central de Conhecimento e Comunicação Interna | Utiliza usuários, funções, setores, unidades e permissões para criar, revisar, publicar e distribuir materiais internos, acompanhar leituras e manter versões |

## 5.1 Regras de integração

- [ ] Definir identificadores únicos.
- [ ] Definir relacionamentos entre registros.
- [ ] Evitar duplicidade.
- [ ] Padronizar serviços de acesso aos dados.
- [ ] Definir validações compartilhadas.
- [ ] Definir tratamento de erros.
- [ ] Garantir permissões em cada operação.
- [ ] Testar fluxos entre módulos.
- [ ] Preservar histórico e rastreabilidade.

A liberação gradual não significa desenvolver módulos isolados. Cada módulo novo deverá utilizar os serviços e registros já existentes.

# 6. DEMAIS MÓDULOS OPERACIONAIS

## 6.1 Internamento

- [ ] Entrada do paciente.
- [ ] Motivo da internação.
- [ ] Médico responsável.
- [ ] Parâmetros clínicos.
- [ ] Evolução.
- [ ] Medicações.
- [ ] Procedimentos.
- [ ] Alimentação.
- [ ] Cuidados.
- [ ] Intercorrências.
- [ ] Alta.
- [ ] Histórico.
- [ ] Integração com atendimento.

## 6.2 Vacinação

- [ ] Cadastro de vacinas.
- [ ] Fabricante.
- [ ] Lote.
- [ ] Validade.
- [ ] Dose.
- [ ] Via de aplicação.
- [ ] Data.
- [ ] Profissional responsável.
- [ ] Próximo reforço.
- [ ] Histórico vacinal.
- [ ] Alertas.

## 6.3 Estoque

- [ ] Cadastro de produtos.
- [ ] Cadastro de medicamentos.
- [ ] Fornecedores.
- [ ] Entradas.
- [ ] Saídas.
- [ ] Saldo.
- [ ] Lotes.
- [ ] Validade.
- [ ] Estoque mínimo.
- [ ] Histórico de movimentações.
- [ ] Identificação do responsável.
- [ ] Controle independente por unidade.

## 6.4 Caixa e financeiro

- [ ] Contas a receber.
- [ ] Contas a pagar.
- [ ] Recebimentos.
- [ ] Despesas.
- [ ] Fluxo de caixa.
- [ ] Formas de pagamento.
- [ ] Relacionamento com atendimentos.
- [ ] Relatórios.
- [ ] Permissões financeiras.
- [ ] Fechamento por unidade.
- [ ] Visão consolidada autorizada.

## 6.5 Relatórios e indicadores

- [ ] Atendimentos.
- [ ] Pacientes.
- [ ] Vacinação.
- [ ] Internamentos.
- [ ] Estoque.
- [ ] Financeiro.
- [ ] Indicadores por unidade.
- [ ] Indicadores consolidados.
- [ ] Filtros por período.
- [ ] Exportação.

## 6.6 MÓDULO — CALCULADORA DE DOSES

**Status: Planejado.** Funcionalidade aprovada para desenvolvimento futuro. Ainda não implementada.

Objetivo: disponibilizar uma ferramenta de apoio ao cálculo matemático de volumes de medicamentos, com interface inspirada na referência visual apresentada pelo usuário.

- [ ] Criar interface própria para a calculadora, integrada à área de Medicações.
- [ ] Permitir informar ou selecionar o paciente e utilizar seu peso atualizado, quando disponível.
- [ ] Informar a dose prescrita pelo médico-veterinário.
- [ ] Informar a concentração e a apresentação disponíveis do medicamento.
- [ ] Calcular o volume correspondente, com conversões de unidades devidamente validadas.
- [ ] Apresentar claramente os dados utilizados e o resultado do cálculo.
- [ ] Exibir alertas para conferência de peso, dose, concentração, apresentação e unidade antes da administração.
- [ ] Prever integração com cadastro de medicamentos, atendimento, prontuário e internamento.
- [ ] Avaliar registro do cálculo no histórico do paciente, conforme fluxo clínico e decisão de projeto a ser definida na implementação.
- [ ] Testar cálculos, conversões, limites, entradas inválidas e comportamento em diferentes dispositivos.

**Regras de segurança:** a calculadora deverá executar somente o cálculo matemático com os parâmetros informados e prescritos. Não deverá sugerir ou definir doses terapêuticas automaticamente, substituir a avaliação do médico-veterinário nem confirmar a administração do medicamento. Os resultados deverão ser conferidos por profissional habilitado antes do uso clínico.

## 6.7 MÓDULO — TREINAMENTO E CAPACITAÇÃO DE FUNCIONÁRIOS

**Status: Planejado.** Funcionalidade aprovada para desenvolvimento futuro. Ainda não implementada.

Objetivo: organizar treinamentos internos, padronizar procedimentos e acompanhar a capacitação dos colaboradores de cada organização.

- [ ] Criar biblioteca de treinamentos com materiais em texto, documentos e vídeos.
- [ ] Permitir organizar conteúdos por assunto, setor, função e nível de conhecimento.
- [ ] Criar trilhas de aprendizagem para funções como médico-veterinário, auxiliar, recepção e financeiro.
- [ ] Permitir que gestores autorizados atribuam treinamentos obrigatórios ou opcionais a colaboradores, funções ou unidades.
- [ ] Definir prazos, periodicidade e regras de reciclagem quando aplicável.
- [ ] Registrar início, progresso, conclusão e pendências de cada treinamento.
- [ ] Permitir avaliações, questionários e critérios mínimos de aprovação.
- [ ] Registrar responsável pelo conteúdo, versão do material e data de disponibilização.
- [ ] Manter histórico individual de capacitações e evidências de conclusão.
- [ ] Disponibilizar relatórios para gestores autorizados, com filtros por colaborador, função, unidade, treinamento e período.
- [ ] Controlar permissões de criação, edição, atribuição e consulta.
- [ ] Garantir que o acesso aos registros respeite o isolamento entre organizações.

**Regras de integração e segurança:** utilizar os usuários, funções, permissões e unidades já existentes. A conclusão de um treinamento deverá ser registrada somente após confirmação efetiva do banco de dados. Alterações em um conteúdo não deverão apagar o histórico de versões ou conclusões anteriores.

## 6.8 MÓDULO — ASSINATURA ELETRÔNICA/DIGITAL E GESTÃO DOCUMENTAL

**Status: Planejado.** Funcionalidade aprovada para desenvolvimento futuro. Ainda não implementada.

Objetivo: permitir a preparação, envio, assinatura, armazenamento e consulta de documentos vinculados à rotina clínica e administrativa do Vetinos.

- [ ] Criar gestão de modelos de documentos e termos.
- [ ] Permitir gerar documentos vinculados ao tutor, paciente, atendimento, internamento ou procedimento.
- [ ] Prever termos de consentimento e autorização, incluindo internação, alta, anestesia, cirurgia e procedimentos.
- [ ] Permitir assinatura por tutores, responsáveis legais e profissionais, conforme o tipo de documento.
- [ ] Definir identificação e autenticação do signatário compatíveis com o nível de segurança exigido.
- [ ] Registrar data e hora, identidade declarada e método de autenticação, versão do documento e evidências técnicas disponíveis.
- [ ] Preservar integridade do documento assinado, com mecanismo de verificação de alterações e trilha de auditoria.
- [ ] Permitir consulta, impressão e exportação do documento final, por exemplo em PDF.
- [ ] Manter histórico de documentos, assinaturas, cancelamentos e eventuais novas versões, sem sobrescrever evidências anteriores.
- [ ] Controlar acesso aos documentos conforme organização, unidade, vínculo com o atendimento e permissões do usuário.
- [ ] Avaliar integração com um provedor especializado de assinatura, caso os requisitos técnicos ou jurídicos exijam.
- [ ] Definir política de retenção, armazenamento, backup e recuperação dos documentos.

**Regras legais e de segurança:** distinguir assinatura eletrônica simples, avançada e qualificada/digital, sem presumir que todas possuem o mesmo nível de validade ou que uma modalidade atende a qualquer documento. Os requisitos deverão ser avaliados conforme a legislação brasileira, a finalidade do documento e o nível de evidência necessário, com validação jurídica antes da liberação. O sistema não deverá declarar validade jurídica automática sem que os requisitos aplicáveis tenham sido verificados.

## 6.9 MÓDULO — MONITORAMENTO DE TRANSFUSÃO SANGUÍNEA

**Status: Planejado.** Funcionalidade aprovada para desenvolvimento futuro. Ainda não implementada.

Objetivo: disponibilizar uma tabela de acompanhamento da transfusão sanguínea, vinculada ao paciente e ao internamento, para registrar parâmetros, horários e possíveis intercorrências durante o procedimento.

- [ ] Criar registro de transfusão vinculado ao paciente, internamento e profissional responsável.
- [ ] Registrar indicação, tipo de hemocomponente, identificação da bolsa, lote ou código de rastreio, volume e dados relevantes do produto.
- [ ] Registrar verificações pré-transfusionais e informações de compatibilidade, conforme protocolo definido pelo médico-veterinário responsável.
- [ ] Criar tabela de monitoramento com horário e parâmetros clínicos antes, durante e após a transfusão.
- [ ] Permitir configurar os intervalos de monitoramento conforme protocolo clínico adotado pela instituição e orientação do médico-veterinário responsável.
- [ ] Registrar temperatura, frequência cardíaca, frequência respiratória, pressão arterial, mucosas e outros parâmetros definidos pelo protocolo.
- [ ] Registrar sinais de reação transfusional, intercorrências, condutas adotadas e evolução.
- [ ] Identificar o profissional responsável por cada registro, com data e hora.
- [ ] Permitir encerrar a transfusão com resumo do procedimento e observações.
- [ ] Integrar o registro ao histórico clínico e ao internamento.
- [ ] Preservar rastreabilidade e histórico de alterações.
- [ ] Testar permissões, consistência dos horários, campos obrigatórios e uso em dispositivos móveis.

**Regras clínicas e de segurança:** o módulo será uma ferramenta de registro e acompanhamento. Não deverá prescrever protocolos, definir parâmetros clínicos automaticamente ou substituir a avaliação do médico-veterinário. Os intervalos, limites e condutas deverão ser definidos e validados por profissional habilitado e pela instituição.


## 6.10 MÓDULO — CENTRAL DE CONHECIMENTO, COMUNICAÇÃO E DOCUMENTOS INTERNOS

**Status: Planejado.** Funcionalidade aprovada para desenvolvimento futuro. Ainda não implementada.

Objetivo: permitir que o gestor da organização ou unidade, ou colaboradores formalmente delegados, criem, redijam, organizem e disponibilizem materiais diretamente no Vetinos, direcionando cada conteúdo aos setores, funções, unidades ou colaboradores correspondentes.

- [ ] Criar uma biblioteca central de conteúdos internos, com organização por categorias, assuntos, setores e funções.
- [ ] Disponibilizar editor de texto dentro do sistema para redigir e formatar comunicados, orientações, manuais, instruções de trabalho e procedimentos operacionais padrão (POP).
- [ ] Permitir anexar materiais complementares, como PDFs, imagens, vídeos e outros formatos definidos na implementação.
- [ ] Disponibilizar modelos reutilizáveis para documentos e comunicados recorrentes.
- [ ] Permitir salvar conteúdos como rascunho, editar, revisar, aprovar, publicar, arquivar e, quando aplicável, programar a publicação.
- [ ] Permitir direcionar cada publicação para toda a organização, unidades específicas, setores, funções ou colaboradores selecionados.
- [ ] Permitir que o gestor delegue permissões específicas para criar, redigir, editar, revisar, aprovar, publicar e arquivar conteúdos, sem conceder automaticamente acesso administrativo completo.
- [ ] Disponibilizar os materiais aos usuários destinatários em uma área própria do sistema, com indicação de conteúdos novos, atualizados e pendentes de leitura.
- [ ] Permitir exigir confirmação de leitura e registrar usuário, data e hora da confirmação.
- [ ] Disponibilizar acompanhamento gerencial de visualizações, confirmações de leitura e pendências, com filtros por conteúdo, setor, função, unidade e colaborador.
- [ ] Permitir definir validade, data de revisão e necessidade de republicação ou nova confirmação quando um material for atualizado.
- [ ] Manter histórico de versões, autoria, responsáveis pela revisão e publicação, datas e alterações relevantes, sem sobrescrever evidências anteriores.
- [ ] Permitir busca e consulta dos materiais conforme as permissões do usuário.
- [ ] Prever notificações internas aos destinatários quando houver nova publicação, atualização ou prazo de leitura.
- [ ] Integrar conteúdos de capacitação à biblioteca e às trilhas do módulo de Treinamento e Capacitação de Funcionários.
- [ ] Permitir encaminhar documentos que exijam ciência formal ao módulo de Assinatura Eletrônica/Digital, quando aplicável.
- [ ] Testar permissões de criação e publicação, direcionamento por setor, confirmação de leitura, histórico de versões, anexos e uso em dispositivos móveis.

**Regras de integração e segurança:** utilizar os usuários, funções, setores, unidades e permissões já existentes, respeitando o isolamento entre organizações. O gestor deverá controlar as delegações e o alcance das publicações. A confirmação de leitura deverá ser tratada como evidência de ciência, não como assinatura eletrônica ou concordância formal. Quando um documento exigir assinatura, deverá utilizar o fluxo próprio de assinatura eletrônica/digital. Publicações, confirmações e alterações de permissão somente poderão ser consideradas concluídas após confirmação efetiva do banco de dados.

# 7. DISPONIBILIZAÇÃO GRADUAL

Os módulos serão liberados conforme forem concluídos e validados.

Estados possíveis:

- Planejado.
- Em desenvolvimento.
- Disponível para testes.
- Validado.
- Disponível no ambiente OFICIAL.

A liberação de um módulo deverá considerar:

1. Implementação funcional.
2. Integração com os módulos existentes.
3. Permissões e segurança.
4. Testes de fluxo completo.
5. Tratamento de erros.
6. Validação no ambiente TESTES.
7. Autorização para liberação no ambiente OFICIAL.

A primeira validação prática poderá ser feita com uma organização parceira, utilizando apenas os módulos liberados e autorizados.

# 8. MONITORAMENTO DE INFRAESTRUTURA E COTAS

## 8.1 Objetivo

Criar monitoramento centralizado no painel MASTER para acompanhar a infraestrutura global do Vetinos.

O monitoramento não deverá expor dados clínicos das organizações.

## 8.2 Indicadores

- Leituras.
- Gravações.
- Exclusões.
- Armazenamento.
- Transferência.
- Custos.
- Erros de gravação.
- Indisponibilidade.
- Estado dos serviços.

Os indicadores deverão ser conciliados com as métricas oficiais do provedor. Não presumir que métricas de aplicação representam integralmente o consumo faturável.

## 8.3 Níveis de atenção

| Nível | Comportamento planejado |
|---|---|
| 50% | Aviso discreto no MASTER |
| 70% | Alerta ao administrador e prevenção |
| 90% | Modo de proteção e suspensão seletiva de operações não essenciais |
| 100% ou falha real | Bloqueio de operações que não possam ser confirmadas com segurança |

Os percentuais deverão ser configuráveis no MASTER, sem confundir configuração interna com alteração das cotas do provedor.

## 8.4 Operações não essenciais

Podem ser limitadas preventivamente:

- Personalização visual.
- Alteração de logotipo.
- Relatórios não urgentes.
- Exportações em massa.
- Downloads administrativos.
- Sincronizações administrativas não urgentes.

## 8.5 Operações essenciais

Recebem prioridade:

- Atendimento.
- Prontuário.
- Internamento.
- Administração de medicamentos.
- Registro de intercorrências.
- Operações clínicas necessárias.

Prioridade não significa garantia de funcionamento quando o banco estiver indisponível.

Pagamentos, movimentações financeiras e registros clínicos não poderão ser considerados concluídos sem confirmação da gravação.

## 8.6 Falha de gravação

Regra obrigatória:

**Sem confirmação do banco, não existe salvamento confirmado.**

Quando uma gravação falhar:

- Não apresentar mensagem de sucesso.
- Não simular gravação.
- Não informar que salvará posteriormente.
- Não executar salvamento silencioso após a recuperação.
- Informar que o registro não foi salvo.
- Orientar o usuário a contatar o responsável pelo sistema.
- Registrar a ocorrência técnica quando houver infraestrutura disponível.
- Notificar o administrador para verificar o problema.

Mensagem ao usuário:

> Não foi possível salvar este registro. O banco de dados não confirmou a gravação. Entre em contato com o responsável pelo sistema.

Alerta ao administrador:

> O Vetinos identificou uma falha de gravação. Verifique o ambiente, o módulo afetado e a disponibilidade do banco de dados.

O alerta deverá registrar, quando disponível:

- Data e horário.
- Ambiente.
- Organização e unidade por identificadores internos.
- Módulo.
- Tipo de operação.
- Código ou categoria do erro.
- Identificador técnico da ocorrência.

Evitar incluir informações clínicas desnecessárias nos alertas.

# 9. TESTES DE INDISPONIBILIDADE

Os testes serão executados exclusivamente no ambiente TESTES.

## 9.1 Teste de indisponibilidade

- [ ] Criar dados fictícios.
- [ ] Executar gravação normal.
- [ ] Confirmar registro salvo.
- [ ] Simular indisponibilidade do banco.
- [ ] Tentar criar um registro.
- [ ] Confirmar que não foi salvo.
- [ ] Verificar mensagem ao usuário.
- [ ] Verificar alerta ao administrador.
- [ ] Restaurar conexão.
- [ ] Confirmar que não houve salvamento automático.
- [ ] Confirmar que o usuário precisa realizar nova operação conscientemente.

## 9.2 Teste de limite de uso

O limite de uso deverá ser testado de maneira controlada.

- [ ] Identificar cotas aplicáveis.
- [ ] Definir mecanismo de simulação.
- [ ] Testar alertas percentuais.
- [ ] Testar tratamento de erros de limite.
- [ ] Verificar comportamento do sistema.
- [ ] Confirmar que nenhuma gravação sem confirmação é apresentada como salva.

Não esgotar cotas reais nem provocar custos desnecessários. Simulação controlada de erros e testes reais de indisponibilidade deverão ser documentados separadamente.

## 9.3 Recuperação

- [ ] Restaurar conexão.
- [ ] Confirmar funcionamento das operações.
- [ ] Verificar integridade dos dados.
- [ ] Confirmar ausência de gravações duplicadas.
- [ ] Confirmar que registros não salvos não foram recriados automaticamente.
- [ ] Registrar resultado do teste.

# 10. PAINEL MASTER

- [ ] Acesso administrativo exclusivo.
- [ ] Cadastro de organizações.
- [ ] Cadastro de unidades.
- [ ] Ativação e suspensão.
- [ ] Gestão de usuários.
- [ ] Gestão de planos.
- [ ] Configuração de preços.
- [ ] Limites por plano.
- [ ] Consumo de infraestrutura.
- [ ] Monitoramento global.
- [ ] Alertas técnicos.
- [ ] Histórico administrativo.
- [ ] Gestão de solicitações.
- [ ] Indicadores consolidados.

A área MASTER deverá possuir proteção reforçada e privilégios separados dos usuários das organizações.

# 11. PLANOS E MODELO COMERCIAL

- [ ] Definir planos mensais.
- [ ] Definir planos anuais.
- [ ] Definir limites por plano.
- [ ] Definir número de unidades incluídas.
- [ ] Definir valor de unidades adicionais.
- [ ] Permitir configuração no MASTER.
- [ ] Exibir condições comerciais no site.
- [ ] Definir política de atualização de preços.
- [ ] Definir contratos e renovação.
- [ ] Avaliar integração de pagamentos.

Preços públicos permanecem em formação até decisão comercial.

Alterações futuras de preço não deverão modificar automaticamente contratos vigentes sem política e condições formalizadas.

# 12. PARCERIAS E VALIDAÇÃO

Está prevista a validação prática com uma organização parceira.

A parceira poderá:

- Utilizar os módulos liberados.
- Informar dificuldades.
- Identificar falhas.
- Sugerir melhorias.
- Validar fluxos reais.
- Participar da evolução do produto.

A participação como parceira de validação não significa que todos os módulos estejam disponíveis.

Possíveis investimentos deverão ser tratados por instrumentos formais, com prestação de contas e condições negociadas separadamente.

# 13. APRESENTAÇÃO COMERCIAL E SITE

- [ ] Manter apresentação comercial no site.
- [ ] Utilizar o documento comercial como referência.
- [ ] Atualizar módulos apresentados conforme evolução real.
- [ ] Diferenciar recursos disponíveis e planejados.
- [ ] Exibir condições comerciais definidas.
- [ ] Criar formulário de interesse de investidores.
- [ ] Criar fluxo seguro de recebimento das solicitações.
- [ ] Definir domínio próprio.
- [ ] Definir identidade visual definitiva.

# 14. BACKUP, PORTABILIDADE E SINCRONIZAÇÃO

- [ ] Definir política de backup.
- [ ] Configurar backups compatíveis com o provedor.
- [ ] Definir retenção.
- [ ] Testar restauração.
- [ ] Documentar recuperação de desastre.
- [ ] Planejar exportação dos dados de uma organização.
- [ ] Planejar portabilidade.
- [ ] Desenvolver camada intermediária de acesso aos dados.
- [ ] Avaliar futura operação local com sincronização.

Backup e exportação de dados são recursos diferentes e deverão ser tratados separadamente.

# 15. CRITÉRIOS DE STATUS

| Status | Significado |
|---|---|
| Planejado | Previsto, ainda sem implementação |
| Em desenvolvimento | Implementação iniciada |
| Disponível para testes | Implementado para validação |
| Validado | Testado e aprovado |
| Disponível no OFICIAL | Liberado para uso real |

Nenhuma funcionalidade poderá avançar de status sem evidências correspondentes.

# 16. REGISTRO DE DECISÕES

Decisões arquiteturais e comerciais importantes deverão ser registradas aqui ou em documentação complementar.

Cada decisão deverá informar:

- Data.
- Descrição.
- Motivo.
- Impactos.
- Estado.
- Pendências.

# 17. PRINCÍPIO DE EVOLUÇÃO

O Vetinos será construído como uma plataforma integrada.

Cada módulo deverá aproveitar os cadastros, serviços, permissões e estruturas já existentes.

Não desenvolver funcionalidades isoladas que provoquem duplicidade de dados ou dificultem a evolução futura.

**EVOLUIR, INTEGRAR E PROTEGER.**
