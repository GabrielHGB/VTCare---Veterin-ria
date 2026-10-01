# VetCare — Veterinária

O **VetCare** é um projeto de site para uma clínica veterinária desenvolvido com **HTML e CSS**, sem utilização de JavaScript. A proposta da atividade foi transformar o planejamento visual feito no Figma em uma aplicação navegável, responsiva e funcional, utilizando recursos nativos do HTML e do CSS para criar interações entre as páginas.

O site apresenta os principais serviços da clínica, profissionais disponíveis, informações individuais de cada veterinário, detalhes dos serviços, fluxo de agendamento, página institucional e contato.

<p align="center">
  <img src="./Assets/VetCare_ Cuidado que Acolhe.png" alt="VetCare - Cuidado veterinário com acolhimento, confiança e ciência" width="90%">
</p>

## Figma

O planejamento do projeto foi desenvolvido no Figma e está dividido em três partes principais:

- **Fluxo:** representação do caminho de navegação entre as telas;
- **Wireframe:** definição inicial da estrutura e organização das páginas;
- **UI:** construção da interface final, incluindo cores, tipografia, componentes e identidade visual.

[Acessar o projeto no Figma](https://www.figma.com/design/pW5ROU2mi9FQd21cMw1YEF/Veterin%C3%A1ria-PD-Case?node-id=22-937&t=DKiCQKXATERlFJIb-1)

## Vercel

O projeto também foi publicado na Vercel para facilitar a visualização e os testes diretamente pelo navegador.

Por meio do deploy é possível acessar a versão final do site, navegar entre as páginas e testar o comportamento responsivo da aplicação.

[Acessar o projeto na Vercel](https://vtcareveterinaria.vercel.app/)

## Tecnologias utilizadas

- HTML5;
- CSS3;
- Google Fonts;
- Figma para prototipação, fluxo e interface;
- Git e GitHub para versionamento do projeto.

As fontes utilizadas no projeto são **Fraunces**, principalmente nos títulos, e **Work Sans**, utilizada nos demais textos da interface.

## Desenvolvimento da atividade

A implementação foi realizada a partir das telas planejadas no Figma. O HTML foi organizado utilizando elementos semânticos como `header`, `nav`, `main`, `section`, `article`, `form`, `figure` e `footer`, enquanto o CSS foi separado de acordo com a responsabilidade de cada página.

O arquivo `Style.css` concentra variáveis, reset e estilos base. O arquivo `Global.css` contém elementos compartilhados entre as páginas, como cabeçalho, navegação e rodapé. Cada página possui também seu próprio arquivo CSS, facilitando a organização e manutenção do projeto.

A interface foi construída seguindo uma estratégia responsiva, com adaptações específicas para celular, tablet e desktop.

## Estratégias utilizadas sem JavaScript

Um dos principais objetivos da atividade foi manter o projeto funcional utilizando apenas HTML e CSS. Para isso, algumas interações normalmente feitas com JavaScript foram substituídas por estratégias utilizando seletores, estados e animações do próprio CSS.

### Menu mobile com checkbox

O menu de navegação para telas menores utiliza um `input` do tipo `checkbox`. Quando o checkbox é marcado, o seletor `:checked` altera a exibição da navbar e transforma visualmente o botão do menu.

Essa estratégia permite abrir e fechar o menu mobile sem JavaScript.

### Filtros de serviços

Na página de serviços, os filtros são construídos com `input type="radio"` e `label`.

O CSS utiliza `:checked` para identificar qual categoria foi selecionada e esconde os cards que não pertencem ao filtro ativo.

Dessa forma, é possível filtrar entre categorias como higiene, prevenção e acompanhamento utilizando apenas CSS.

### Filtros de profissionais

A página de veterinários utiliza a mesma ideia dos filtros de serviços. Os profissionais podem ser filtrados por especialidade através de radio buttons e seletores CSS.

No mobile, a área de filtros possui scroll horizontal para permitir a navegação entre todas as opções sem ultrapassar os limites da tela.

### Conteúdo dinâmico com `:target`

As páginas de detalhes do serviço, profissionais, perfil do veterinário e agendamento utilizam o hash presente na URL para determinar qual conteúdo deve aparecer.

Um endereço como:

```text
perfil-veterinario.html#banho-tosa--dra-camila-rocha
```

faz com que o elemento correspondente ao identificador seja selecionado através de `:target`.

Em conjunto com `:has()`, essa estratégia permite esconder o conteúdo padrão e exibir somente a opção correspondente ao caminho escolhido pelo usuário.

Isso possibilita reutilizar uma mesma página para diferentes serviços e profissionais, evitando a criação de um arquivo HTML diferente para cada combinação.

### Carrosséis com `@keyframes`

Os carrosséis presentes na página inicial foram desenvolvidos utilizando animações CSS com `@keyframes`.

O trilho do carrossel é movimentado horizontalmente através de `transform:translateX()`, fazendo com que os serviços e profissionais sejam apresentados automaticamente no mobile sem necessidade de scripts.

Em telas maiores, os conteúdos passam a ser apresentados em grid.

### Revisão do agendamento

O fluxo de agendamento também utiliza um checkbox como controle de estado.

Ao selecionar **Revisar agendamento**, o CSS altera a interface para o modo de confirmação. Os mesmos campos preenchidos pelo usuário continuam na página, porém recebem um estilo diferente para funcionar visualmente como um resumo dos dados.

Assim, os valores dos campos não precisam ser copiados para novos elementos, o que permitiria apenas com JavaScript. O próprio input permanece com seu valor e apenas sua apresentação visual é modificada.

Ao confirmar o agendamento, o usuário retorna para a página inicial do projeto.

## Responsividade

O projeto foi organizado em três faixas principais de tela:

```text
Mobile:  até 699px
Tablet:  700px até 999px
Desktop: 1000px ou mais
```

A estrutura das páginas é adaptada de acordo com o espaço disponível. Entre as principais mudanças estão:

- alteração de layouts em coluna para grid;
- menu mobile em telas menores;
- filtros com scroll horizontal no celular;
- carrosséis no mobile e grids em telas maiores;
- ajustes de espaçamento, tamanho dos elementos e margens de segurança;
- reorganização dos formulários em uma ou duas colunas.

## Fluxo principal do site

O fluxo principal de navegação foi estruturado da seguinte forma:

```text
Home
  |
  v
Serviços
  |
  v
Detalhes do serviço
  |
  v
Veterinários
  |
  v
Perfil do veterinário
  |
  v
Agendamento
```

A Home também permite acesso direto às páginas **Sobre** e **Contato** através da navegação principal.

## Páginas do projeto

O projeto é composto pelas seguintes páginas:

- `index.html` — página inicial;
- `servicos.html` — listagem e filtros dos serviços;
- `detalhes-servico.html` — informações específicas de cada serviço;
- `veterinarios.html` — listagem e filtros dos profissionais;
- `perfil-veterinario.html` — informações individuais dos veterinários;
- `agendamento.html` — formulário e revisão visual do agendamento;
- `sobre.html` — informações sobre a clínica;
- `contato.html` — informações e formas de contato.

## Estrutura de pastas

```text
VTCare---Veterin-ria/
|
|-- Assets/
|   |-- banho-tosa.png
|   |-- check-up.png
|   |-- clinica-dentro.png
|   |-- clinica-fora.png
|   |-- dr-andre-silva.png
|   |-- dr-lucas-martins.png
|   |-- dra-camila-rocha.png
|   |-- mapa-vetcare.png
|   |-- vacinacao.png
|   `-- vetcare-readme.png
|
|-- Paginas/
|   |-- agendamento.html
|   |-- contato.html
|   |-- detalhes-servico.html
|   |-- perfil-veterinario.html
|   |-- servicos.html
|   |-- sobre.html
|   `-- veterinarios.html
|
|-- Styles/
|   |-- Agendamento.css
|   |-- Contato.css
|   |-- DetalhesServico.css
|   |-- Global.css
|   |-- Home.css
|   |-- PerfilVeterinario.css
|   |-- Servicos.css
|   |-- Sobre.css
|   |-- Style.css
|   `-- Veterinarios.css
|
|-- index.html
`-- README.md
```

## Como executar

O projeto não necessita de instalação de dependências ou processo de build.

Basta abrir o arquivo `index.html` diretamente no navegador. Para facilitar o desenvolvimento, também é possível utilizar uma extensão como **Live Server** no Visual Studio Code.

```text
1. Abra a pasta do projeto no VS Code.
2. Abra o arquivo index.html.
3. Execute com o Live Server ou abra o arquivo diretamente no navegador.
```

## Observações

O projeto foi desenvolvido como uma aplicação front-end estática. Por não utilizar JavaScript, backend ou banco de dados, ações como o envio real de formulários e o armazenamento de agendamentos não são realizadas.

O objetivo da atividade foi explorar ao máximo os recursos disponíveis no HTML e no CSS, mantendo o fluxo de navegação, filtros, animações, estados visuais e responsividade próximos ao protótipo criado no Figma.
