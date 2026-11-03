# Intranet YBYX — Conceito inicial

**Status:** Ideia registrada — ainda não aprovada para implementação  
**Categoria:** Produto modular do ecossistema YBYX  
**Modelo pretendido:** SaaS multiempresa, multiunidade e modular  
**Nome:** Provisório — Intranet YBYX

## 1. Visão geral

Criar uma plataforma de intranet empresarial que permita a uma organização centralizar a comunicação interna, o cadastro de suas unidades e a gestão de seus colaboradores.

A solução deverá poder funcionar de duas formas:

- **Como produto independente:** a organização cria sua própria conta e utiliza a intranet diretamente.
- **Como módulo integrado:** a organização contrata ou ativa a intranet dentro de outro produto YBYX compatível, como o VET MAX, acessando seus recursos a partir do próprio sistema principal.

## 2. Organização, unidades e colaboradores

O modelo inicial imaginado segue a lógica:

1. O responsável pela organização cria a conta principal.
2. Dentro dessa conta, cadastra a organização.
3. Caso existam filiais, unidades ou estabelecimentos, cadastra cada uma vinculada à organização principal.
4. Cadastra ou convida os funcionários e define seus vínculos com a organização e, quando aplicável, com uma ou mais unidades.

A estrutura deverá permitir uma visão central da organização, sem perder a possibilidade de organizar informações e acessos por unidade.

## 3. Comunicação interna

A intranet deverá oferecer um ambiente próprio para comunicação e interação entre a organização e seus colaboradores.

A ideia inicial inclui comunicados e avisos importantes, como memorandos, além de recursos de interação interna. O escopo funcional detalhado ainda será definido em etapa posterior.

## 4. Arquitetura modular e integração com o ecossistema YBYX

A intranet deverá ser concebida como um produto modular, com capacidade de integração nativa aos demais sistemas desenvolvidos pela YBYX.

O objetivo é que os produtos sejam compatíveis entre si e que funcionalidades possam ser disponibilizadas como módulos ativáveis, sem exigir que o usuário abandone o sistema principal.

### Exemplo de integração com o VET MAX

Uma clínica ou hospital veterinário que utilize o VET MAX poderá contratar ou ativar o módulo de Intranet. Após a ativação, a opção de acesso à intranet ficará disponível dentro do próprio VET MAX, mantendo uma experiência integrada.

A mesma lógica poderá ser aplicada a outros produtos YBYX compatíveis.

## 5. Conceitos técnicos relacionados

- **Arquitetura modular:** funcionalidades organizadas em módulos com responsabilidades definidas.
- **Plug and Play:** possibilidade de adicionar ou ativar um módulo compatível com pouca intervenção no produto principal.
- **Integração nativa:** comunicação entre produtos do ecossistema YBYX por mecanismos de integração planejados.
- **SaaS multi-tenant:** uma plataforma atende várias organizações, mantendo os dados e os acessos de cada organização devidamente isolados.
- **Multiempresa e multiunidade:** suporte a organizações com várias empresas, filiais ou unidades, conforme o modelo que vier a ser definido.

Esses conceitos orientam a visão do produto; não representam decisões técnicas de implementação já aprovadas.

## 6. Diretrizes e pontos a definir

Antes do desenvolvimento, será necessário detalhar:

- estrutura de organizações, empresas e unidades;
- papéis, permissões e hierarquia de colaboradores;
- cadastro, convite, entrada e desligamento de funcionários;
- módulos e recursos da intranet;
- modelo de contratação, ativação e desativação do módulo;
- autenticação e experiência de acesso quando integrada a outro produto;
- integração, compartilhamento controlado de identidade e isolamento dos dados;
- quais recursos estarão disponíveis no produto independente e quais poderão ser incorporados por outros sistemas.

## 7. Relação com o portfólio YBYX

A Intranet YBYX deverá ser tratada como um produto reutilizável do portfólio da empresa, e não como uma funcionalidade exclusiva do VET MAX.

O VET MAX é o primeiro exemplo de integração considerado nesta ideia. A arquitetura deverá permitir avaliar integrações futuras com outros produtos YBYX.

---

**Registro de origem:** ideia apresentada pelo responsável pelo projeto em 02/11/2026.  
**Próxima etapa:** detalhar o conceito e suas regras de produto antes de iniciar qualquer implementação.
