# Projeto Meets

## Arquivos do Laboratório

- [1. Documento Visão.md](1.%20Documento%20Visão.md)
- [2. Atividades do Negócio.md](2.%20Atividades%20do%20Negócio.md)
- [3. Requisitos do Sistema.md](3.%20Requisitos%20do%20Sistema.md)
- [4. Casos de Uso.md](4.%20Casos%20de%20Uso.md)

## Imagens do Projeto

- [Modelo de dominio](imagens/modelo_dominio.png)
- [Modelo conceitual](imagens/modelo_conceitual.png)
- [Caso de uso](imagens/caso_de_uso.png)
- [Sequencia de login](imagens/sequencia_login.png)
- [Atividade de cadastro de usuario](imagens/atividade_cadastro_usuario.png)
- [Atividade de publicacao de post](imagens/atividade_publicacao_post.png)

## 1. Documento de Visão

O Meets e um sistema de apoio a comunicacao e participacao academica voltado a estudantes e corpo docente. A proposta e centralizar publicacoes, eventos, enquetes, interacoes e registro de historico de atividades em um unico ambiente, permitindo tambem a gestao de denuncias e a atribuicao de pontuacao.

### 1.1 Objetivo

Organizar a troca de informacoes da comunidade academica, facilitar a publicacao de conteudo, apoiar a divulgacao de eventos e manter um mecanismo de controle por meio de autentificacao, logs e pontuacao.

### 1.2 Publico-alvo

- Estudantes
- Corpo docente

### 1.3 Escopo

O sistema contempla:

- Cadastro e autentificacao de usuarios
- Visualizacao de feed
- Publicacao de posts e enquetes
- Interacao com posts e enquetes
- Criacao e visualizacao de eventos
- Denuncia de postagens
- Analise de denuncias pelo corpo docente
- Controle de log e pontuacao

Ficam fora do escopo, nesta versao documentada, integracoes externas nao previstas nos diagramas e funcionalidades administrativas nao representadas no modelo atual.

### 1.4 Beneficios esperados

- Concentrar informacoes academicas em uma unica plataforma
- Melhorar o engajamento entre estudantes e docentes
- Dar visibilidade a eventos e comunicados
- Permitir rastreabilidade de acoes por meio de logs
- Apoiar a moderacao de conteudo com denuncias e analise

## 2. Atividades do Negocio

As atividades de negocio identificadas nos diagramas atuais sao:

### 2.1 Cadastro de usuario

Fluxo principal:

1. O usuario preenche o formulario de cadastro.
2. O sistema valida campos obrigatorios.
3. O sistema verifica se o e-mail ja esta em uso.
4. O sistema valida a senha.
5. Se tudo estiver correto, os dados sao enviados ao controle de autenticacao.
6. O controle solicita armazenamento no banco de dados.
7. O banco grava o novo usuario e confirma o armazenamento.
8. O sistema informa sucesso ao usuario.

Fluxos alternativos:

- Campos vazios: exibir mensagem de erro.
- E-mail ja cadastrado: exibir mensagem de e-mail em uso.
- Senha invalida: exibir mensagem de erro na senha.

### 2.2 Publicacao de post

Fluxo principal:

1. O usuario clica em publicar post.
2. O sistema exibe o formulario de criacao.
3. O usuario preenche o formulario.
4. O sistema valida os dados do post.
5. Se os dados forem validos, o sistema envia as informacoes ao controle de publicacao.
6. O controle solicita armazenamento no banco de dados.
7. O banco grava o novo post e confirma o armazenamento.
8. O sistema exibe o post no feed.

Fluxos alternativos:

- Campos obrigatorios ausentes: exibir mensagem de erro.
- Dados invalidos: exibir mensagem de erro.

## 3. Requisitos do Sistema

### 3.1 Requisitos funcionais

RF01 - Permitir cadastro de usuario.

RF02 - Permitir login com e-mail e senha.

RF03 - Permitir visualizacao do feed.

RF04 - Permitir publicacao de posts.

RF05 - Permitir publicacao de enquetes.

RF06 - Permitir interacao com enquetes.

RF07 - Permitir curtida em post.

RF08 - Permitir comentario em post.

RF09 - Permitir denuncia de post.

RF10 - Permitir visualizacao de eventos.

RF11 - Permitir criacao de evento.

RF12 - Permitir confirmacao de presenca em evento.

RF13 - Permitir analise de denuncias pelo corpo docente.

RF14 - Registrar historico de atividades do usuario.

RF15 - Converter atividades em pontuacao.

RF16 - Deduzir pontuacao do usuario em caso de denuncia procedente.

### 3.2 Requisitos nao funcionais

RNF01 - O sistema deve ser desenvolvido com arquitetura orientada a objetos.

RNF02 - A documentacao deve estar consistente com a implementacao.

RNF03 - O sistema deve possuir persistencia de dados em banco.

RNF04 - O sistema deve manter rastreabilidade de acoes por meio de log.

RNF05 - O sistema deve ser responsivo para uso em mobile e web, quando aplicavel.

RNF06 - O sistema deve apresentar mensagens claras de validacao e erro.

RNF07 - O sistema deve registrar apenas acoes autorizadas por usuario autenticado.

RNF08 - O sistema deve manter consistencia entre cadastro, publicacao e historico.

### 3.3 Regras de negocio

RN01 - O usuario deve possuir e-mail unico no cadastro.

RN02 - O cadastro so pode ser concluido com todos os campos obrigatorios preenchidos.

RN03 - A senha deve atender as regras de validacao definidas pelo sistema.

RN04 - Somente usuarios autenticados podem realizar publicacoes e interacoes.

RN05 - Apenas o corpo docente pode analisar denuncias.

RN06 - Toda acao relevante deve gerar log.

RN07 - A pontuacao deve ser atualizada conforme acoes validas do usuario.

RN08 - Denuncias procedentes podem reduzir a pontuacao do usuario responsavel.

RN09 - Eventos devem possuir dados obrigatorios antes de serem publicados.

RN10 - Enquetes e posts devem ser exibidos no feed apos armazenamento com sucesso.

## 4. Matriz de Relacionamento RN x RF

| RN / RF | RF01 | RF02 | RF03 | RF04 | RF05 | RF06 | RF07 | RF08 | RF09 | RF10 | RF11 | RF12 | RF13 | RF14 | RF15 | RF16 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| RN01 | X |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| RN02 | X |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| RN03 | X | X |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| RN04 |  | X |  | X | X | X | X | X | X |  |  |  |  | X | X |  |
| RN05 |  |  |  |  |  |  |  |  | X |  |  |  | X |  |  | X |
| RN06 |  | X |  | X | X | X | X | X | X | X | X | X | X | X | X | X |
| RN07 |  |  |  | X | X | X | X | X |  |  |  |  |  | X | X | X |
| RN08 |  |  |  |  |  |  |  |  | X |  |  |  | X |  |  | X |
| RN09 |  |  |  |  |  |  |  |  |  | X | X |  |  |  |  |  |
| RN10 |  |  | X | X | X | X | X | X |  | X | X | X |  |  |  |  |

## 5. Diagrama de Entidade e Relacionamento

Com base no modelo conceitual e no diagrama de dominio, as entidades principais sao:

- Usuario
- Estudante
- Corpo_Docente
- Evento
- Log
- Pontuacao
- Post_Reportado

### 5.1 Relacionamentos principais

- Estudante herda de Usuario.
- Corpo_Docente herda de Usuario.
- Estudante cria Evento.
- Estudante gera Log.
- Estudante gera Pontuacao.
- Estudante pode reportar Post_Reportado.
- Corpo_Docente analisa Post_Reportado.

### 5.2 Descricao sintetica das entidades

- Usuario: armazena dados cadastrais, autenticacao e perfil.
- Estudante: representa o usuario que executa interacoes, publicacoes e denuncias.
- Corpo_Docente: representa o perfil com permissao de analise.
- Evento: armazena titulo, descricao, local, categoria, datas, imagem e status.
- Log: registra acoes do sistema e do usuario.
- Pontuacao: controla valor, tipo e data das acoes pontuadas.
- Post_Reportado: registra denuncias, motivo, data e status de analise.

## 6. Diagrama de Classe

O diagrama de classe indica uma estrutura orientada a objetos com as seguintes classes principais:

- Usuario
- Estudante
- Corpo_Docente
- Evento
- Log
- Pontuacao
- Post_Reportado

### 6.1 Responsabilidades das classes

- Usuario: cadastro, consulta de e-mail, verificacao de numero, validacao de senha e login.
- Estudante: denuncias, criacao de eventos e geracao de interacoes.
- Corpo_Docente: analise de denuncias.
- Evento: criacao e verificacao de data.
- Log: registro de atividades.
- Pontuacao: calculo da pontuacao.
- Post_Reportado: desativacao e calculo de pontuacao relacionada a denuncia.

## 7. Diagrama Geral de Caso de Uso

### 7.1 Atores

- Estudante
- Corpo docente

### 7.2 Casos de uso identificados

- Fazer login
- Manter usuario
- Visualizar feed
- Visualizar eventos
- Criar evento
- Confirmar presenca
- Publicar enquete
- Interagir em enquetes
- Curtir post
- Comentar post
- Denunciar post
- Analisar denuncias
- Manter historico de atividades
- Converter atividades em pontuacao
- Deduzir pontuacao do usuario

### 7.3 Observacoes de fluxo

- Fazer login e requisito base para as demais operacoes.
- Visualizar feed concentra as interacoes principais.
- Denuncia de post alimenta o fluxo de analise do corpo docente.
- Historico e pontuacao apoiam o acompanhamento do engajamento.

## 8. Especificacao dos Casos de Uso

### UC01 - Fazer Login

Ator principal: Usuario

Pre-condicao: usuario cadastrado no sistema.

Fluxo principal:

1. Usuario informa e-mail e senha.
2. Sistema valida as credenciais.
3. Sistema consulta os dados do usuario no banco.
4. Sistema confirma as credenciais.
5. Sistema redireciona para a pagina inicial.

Fluxos alternativos:

- Senha incorreta: exibir mensagem de erro.
- Usuario nao encontrado: exibir mensagem de erro.

### UC02 - Cadastrar Usuario

Ator principal: Usuario.

Pre-condicao: usuario nao cadastrado.

Fluxo principal:

1. Usuario preenche formulario de cadastro.
2. Sistema valida campos obrigatorios.
3. Sistema verifica se o e-mail esta cadastrado.
4. Sistema valida a senha.
5. Sistema envia os dados ao controle de autenticacao.
6. Dados sao armazenados no banco.
7. Sistema informa sucesso ao usuario.

Fluxos alternativos:

- Campos vazios: exibir mensagem de erro.
- E-mail em uso: exibir mensagem de email em uso.
- Senha invalida: exibir mensagem de erro na senha.

### UC03 - Publicar Post

Ator principal: Estudante.

Pre-condicao: usuario autenticado.

Fluxo principal:

1. Usuario clica em Publicar Post.
2. Sistema exibe formulario de criacao.
3. Usuario preenche os campos.
4. Sistema valida os dados.
5. Sistema envia os dados ao controle de publicacao.
6. Dados sao armazenados no banco.
7. Sistema exibe o post no feed.

Fluxos alternativos:

- Campos obrigatorios ausentes: exibir mensagem de erro.
- Dados invalidos: exibir mensagem de erro.

### UC04 - Criar Evento

Ator principal: Estudante.

Pre-condicao: usuario autenticado.

Fluxo principal:

1. Usuario informa os dados do evento.
2. Sistema valida os dados.
3. Sistema registra o evento.
4. Sistema exibe o evento na area de eventos.

### UC05 - Denunciar Post

Ator principal: Estudante.

Pre-condicao: usuario autenticado e post visivel.

Fluxo principal:

1. Usuario seleciona a opcao de denunciar.
2. Sistema registra o motivo.
3. Sistema cria o post reportado.
4. Sistema encaminha para analise.

### UC06 - Analisar Denuncias

Ator principal: Corpo docente.

Pre-condicao: existir denuncia pendente.

Fluxo principal:

1. Docente acessa a fila de denuncias.
2. Sistema exibe os registros.
3. Docente analisa o conteudo denunciado.
4. Sistema registra a decisao.
5. Se a denuncia for procedente, o sistema atualiza a pontuacao.

## 9. Diagrama de Sequencia

### 9.1 Login

O fluxo de sequencia de login contem:

- Usuario
- Sistema
- Controle de Autenticacao
- Banco de Dados

Resumo do comportamento:

1. Usuario envia e-mail e senha.
2. Sistema encaminha para validacao.
3. Controle de Autenticacao consulta o banco.
4. Banco retorna os dados do usuario.
5. Controle confirma credenciais validas ou invalidas.
6. Sistema redireciona ou exibe erro conforme o resultado.

### 9.2 Publicacao de post

O fluxo de sequencia de publicacao contem:

- Usuario
- Sistema
- Controle de Publicacao
- Banco de Dados

Resumo do comportamento:

1. Usuario solicita publicar post.
2. Sistema apresenta o formulario.
3. Usuario envia os dados preenchidos.
4. Sistema valida e repassa ao controle de publicacao.
5. Controle solicita persistencia no banco.
6. Banco confirma o armazenamento.
7. Sistema exibe o post no feed.

## 10. Consistencia entre documentos e programacao

Para manter consistencia entre documentacao e implementacao, o projeto Meets deve preservar:

- Nomenclatura unica para entidades e classes.
- Regras de validacao iguais nos diagramas e no codigo.
- Fluxos de login, cadastro, publicacao e denuncia alinhados com a arquitetura.
- Relacionamentos de dominio iguais ao modelo de banco.
- Controle de autenticacao e publicacao separados por responsabilidade.

## 11. Observacoes finais

Este documento consolida a base documental do projeto Meets a partir do material disponivel na pasta do laboratorio e dos diagramas anexos no repositorio. Ele pode ser usado como ponto unico de referencia para a entrega da disciplina, mantendo a mesma linha de requisitos, modelagem e comportamento prevista nos arquivos de apoio.
