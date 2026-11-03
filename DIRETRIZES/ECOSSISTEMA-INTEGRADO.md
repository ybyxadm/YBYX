# Ecossistema Integrado YBYX

## 1. Visão

A YBYX deverá desenvolver um conjunto de produtos digitais capazes de funcionar de forma independente e, quando fizer sentido, integrar-se entre si.

O cliente deverá poder contratar uma solução específica e, posteriormente, ampliar seu ambiente digital adquirindo outros produtos ou módulos pelo Portal do Cliente YBYX.

**Princípio central: uma conta, uma empresa, vários produtos e um ecossistema integrado.**

Esta diretriz registra uma visão estratégica. Não representa autorização para iniciar implementação nem define, por si só, uma arquitetura técnica definitiva.

## 2. Portal do Cliente YBYX

O Portal do Cliente será o ponto central de relacionamento entre a YBYX e as organizações clientes.

A visão inclui:

- acesso centralizado aos produtos e serviços contratados;
- catálogo de produtos, módulos e serviços disponíveis;
- contratação ou solicitação de novos produtos;
- visualização dos módulos compatíveis com cada produto;
- gestão de assinaturas, planos, licenças e situação dos serviços;
- administração da organização, unidades/filiais e colaboradores, conforme as permissões contratadas;
- acesso aos produtos autorizados sem exigir uma conta independente para cada sistema, sempre que a integração de identidade for tecnicamente viável.

## 3. Produtos, módulos e expansão

Cada produto deverá poder ter identidade, finalidade, ciclo de evolução e funcionamento próprios.

Quando aplicável, um produto poderá oferecer módulos adicionais que ampliem suas funcionalidades. O Portal deverá apresentar apenas módulos compatíveis com o produto e com o plano do cliente.

Exemplo de jornada:

1. Uma organização contrata o VET MAX.
2. Pelo Portal do Cliente, consulta e adquire módulos adicionais disponíveis.
3. Pode ativar a Calculadora Vet como módulo integrado ao fluxo do VET MAX.
4. Pode contratar a Intranet Web para comunicação e gestão de avisos internos.
5. Pode contratar um produto de e-commerce para criar sua própria loja virtual e vender produtos pela internet.

A disponibilidade de cada módulo ou integração dependerá de sua implementação, compatibilidade, contratação e autorização.

## 4. Integração entre produtos

Os produtos YBYX deverão ser concebidos para permitir integrações futuras, evitando dependências desnecessárias entre seus códigos e operações.

Diretrizes:

- integração por interfaces e contratos bem definidos;
- compartilhamento de identidade e contexto organizacional quando apropriado;
- comunicação entre sistemas com autenticação, autorização e registro de operações;
- respeito à separação dos dados e às permissões de cada produto;
- possibilidade de utilizar um produto isoladamente, sem obrigar a contratação dos demais;
- módulos devem declarar suas dependências e compatibilidades;
- integrações não devem conceder acesso irrestrito aos dados de outro produto.

A integração deverá ser planejada caso a caso. Nem todos os produtos precisarão compartilhar dados ou oferecer integração direta.

## 5. Organização cliente

A experiência deverá considerar empresas que possuem uma ou mais unidades, filiais, equipes e colaboradores.

O modelo de organização poderá ser utilizado pelos diferentes produtos, respeitando as necessidades de cada segmento. A estrutura de uma empresa no Portal não deverá significar que todos os produtos terão exatamente os mesmos módulos, permissões ou regras operacionais.

## 6. Exemplos do ecossistema

Os exemplos abaixo representam possibilidades em planejamento, não necessariamente produtos já implementados:

| Solução | Finalidade |
|---|---|
| VET MAX | Gestão de clínicas e hospitais veterinários |
| Calculadora Vet | Ferramenta/módulo de apoio a cálculos veterinários, com integração planejada ao VET MAX |
| Intranet Web | Comunicação interna, memorandos e avisos para organizações e equipes |
| E-commerce | Criação de loja virtual própria para empresas que desejam vender seus produtos pela internet |
| Novos produtos YBYX | Soluções de outros segmentos que poderão integrar o ecossistema |

O e-commerce poderá oferecer recursos como catálogo, carrinho, pedidos e integrações com meios de pagamento, estoque e logística, conforme o escopo que vier a ser definido. A referência a plataformas como Mercado Livre e Shopee indica a ambição de oferecer uma experiência de compra online; não determina que o produto será um marketplace de múltiplos vendedores.

## 7. Princípios de negócio

- O cliente poderá começar com um único produto e expandir gradualmente.
- A contratação de um produto não deverá obrigar a contratação de todo o ecossistema.
- O Portal deverá facilitar a descoberta, aquisição e gestão das soluções.
- Produtos poderão ser oferecidos de forma independente ou integrada.
- Planos, preços, licenças e regras comerciais serão definidos por produto e/ou módulo.
- A YBYX deverá conseguir adicionar novas soluções ao catálogo sem reconstruir o Portal a cada lançamento.

## 8. Segurança e governança

A evolução do ecossistema deverá considerar desde o planejamento:

- isolamento entre organizações clientes;
- controle de acesso por usuário, organização, unidade e produto;
- princípio do menor privilégio;
- autenticação e autorização consistentes;
- rastreabilidade de operações relevantes;
- gestão segura de integrações, tokens e credenciais;
- proteção e uso adequado dos dados compartilhados.

## 9. Relação com outras documentações

Esta diretriz orienta a visão geral do ecossistema. Cada produto deverá manter sua própria documentação de conceito, requisitos, arquitetura, compatibilidades e plano de desenvolvimento.

A documentação específica de cada produto deverá detalhar como ele participa do ecossistema, sem presumir funcionalidades ainda não implementadas.

## 10. Status

**Status: visão estratégica registrada — planejamento.**

A implementação do Portal do Cliente, do catálogo comercial, da gestão de assinaturas e das integrações deverá ser definida em etapas próprias, após análise de requisitos e arquitetura.
