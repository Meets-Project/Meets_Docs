# Meets - Atividades do Negocio

## 1. Objetivo

Descrever as principais atividades de negocio executadas no Meets e os fluxos que sustentam o funcionamento da plataforma.

## 2. Cadastro de Usuario

O usuario acessa o formulario de cadastro, preenche os dados obrigatorios e envia as informacoes ao sistema. O sistema valida os campos, verifica duplicidade de e-mail e confirma se a senha atende aos criterios definidos.

Se algum campo estiver ausente, o sistema exibe mensagem de erro. Se o e-mail ja estiver em uso, o sistema informa a duplicidade. Se a senha nao atender aos criterios, o sistema exibe mensagem de invalidacao.

Quando todas as validacoes sao aprovadas, os dados sao enviados ao controle de autenticacao, persistidos no banco de dados e confirmados ao usuario como cadastro concluido.

![Diagrama de atividade de cadastro de usuario](imagens/atividade_cadastro_usuario.png)

## 3. Publicacao de Post

O usuario autenticado seleciona a opcao de publicar post, preenche o formulario e submete os dados ao sistema. O sistema valida os campos obrigatorios e verifica se o conteudo esta consistente para publicacao.

Se houver campos vazios ou informacoes invalidas, o sistema exibe mensagem de erro e retorna ao formulario. Quando a validacao e concluida com sucesso, os dados sao enviados ao controle de publicacao, persistidos no banco e exibidos no feed.

![Diagrama de atividade de publicacao de post](imagens/atividade_publicacao_post.png)

## 4. Observacoes

As atividades acima foram escolhidas por representarem os fluxos centrais observados nos diagramas de atividade do projeto Meets.