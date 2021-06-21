
# Teste para tutor/desenvolvedor PHP

## Tecnologias
- PHP
- Laravel
- MySQL
- Angular ou React ou Vue
- Docker


## Descrição

Criar um software que administra uma biblioteca de imagens.
O software será dividido em duas aplicações:

* Back-end será uma API Rest feito em Laravel
* Front-end será feito como uma Single Page Application em uma destas três tecnologias: Angular, React ou Vue.

## Regras do negócio

- Todas as informações serão armazenadas no MySQL.
- As imagens precisam armazenar nome e descrição.
- As imagens deverão ser identificáveis por UUID em vez de um ID inteiro convencional que será administrado pelo Laravel.
- As imagens precisam ser categorizadas, uma imagem pode estar relacionada com várias categorias, por isso é necessário criar um cadastro de categoria somente com o nome da categoria.
- As imagens precisam ser facilmente pesquisáveis ou por nome, ou por descrição ou por categorias.
- Deverá ser possível incluir uma imagem no sistema passando todas as informações, assim como várias de uma vez. Todas as informações deverão ser validadas:
  - O campo nome é obrigatório e deverá ter no máximo 255 caracteres.
  - O campo descrição é obrigatório e não tem limites para armazenamento.
  - As categorias relacionadas deverão ser verificadas no momento do cadastro.
  - As imagens a serem incluídas deverão ter o tamanho máximo de 20MB e deverão ser somente do tipo png, gif ou jpeg.
- Se uma imagem tiver sido cadastrada de forma incorreta, não poderá ser possível altera-la, somente apaga-la, mas deverá ser uma exclusão lógica que poderá ser possível de pesquisar ou recuperar mais tarde.
- Somente usuários autenticados poderão realizar qualquer tarefa no sistema. A autenticação implementada será a JWT.
- Teremos dois níveis de usuário: Admin e Comum. O usuário comum, pode incluir imagens e categorias, mas não pode editar, nem exclui-las somente o Admin.
- Não é necessário criar o cadastro de usuário. O sistema já deverá vir com dois usuários por padrão: admin@user.com (permissão de admin), user@user.com (permissão comum).


## API Rest com Laravel

- A API Rest deverá ser autenticada com JWT.
- Segue os endpoints a serem criados:
   - Endpoints das imagens
     - GET    /images
     - GET    /images/:id
     - POST   /images
     - DELETE /images/:id
   - Endpoints das categorias
     - GET    /categories
     - GET    /categories/:id
     - POST   /categories
     - PUT    /categories
     - DELETE /categorias/:id
- Os endpoints deverão ser documentados pelo Swagger. A documentação da API ficará no endereço /api/doc.
- Deve-se usar a arquitetura REST a risca prestando atenção as boas práticas de Content Negotiation, HTTP Response e Status Code.

## Front-end

- O front-end deverá ser responsivo.
- O front-end deverá ser autenticado pela API Rest. Use as boas práticas deste tipo de autenticado.
- Crie as ações no front-end de acordo com a API Rest, pode-se criar páginas para listagem ou cadastro, bem como pode ser modals, mostre sua criatividade.
- A listagem das imagens deverá ser bem responsivo, imagens com tamanho diferentes deverão se ajustar bem ao tamanho da tela. A listagem também deverá prover um modo fácil de realizar a pesquisa das imagens de acordo com a regra de negócio.
- Os formulários de cadastro deverão validar as informações também no front-end e mostrar os erros de forma adequado ao usuário.

## Docker

Todo projeto deverá ser desenvolvido com Docker e Docker Compose. Uma vez que se rode `docker-compose up` todo o projeto deverá rodar completamente. O projeto deverá rodar facilmente em todos os sistemas operacionais: Mac, Linux e Windows.

## Vídeo-aula

Você deverá gravar 4 aulas, cada aula não deve passar de 15 min. Aulas deverão ser gravadas com a utilização de câmera.

Duas aulas deverão ser codificando alguma parte do sistema (de sua escolha) no ato da aula. 

Duas aulas deverão explicar alguma parte do sistema já criado, o objetivo da aula será focar na explicação da implementação e explicar os motivos desta implementação.

Explique com clareza o que será desenvolvido, monte sua didática para que um aluno consiga entende-la facilmente.

## Entrega

Entregue o projeto em um repositório Git remoto (as 4 aulas deverão estar presentes no repositório, renderize-as em baixa qualidade) e envie o link para o e-mail: rafael@schoolofnet.com
