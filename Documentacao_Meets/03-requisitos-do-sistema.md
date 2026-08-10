# Meets - Requisitos do Sistema

## 1. Objetivo

Registrar os requisitos funcionais, nao funcionais e regras de negocio do sistema Meets, mantendo a relacao entre o comportamento esperado e a documentacao UML.

## 2. Requisitos Funcionais

### Autenticacao

- RF01 - Cadastrar usuario.
- RF02 - Realizar login com e-mail e senha.

### Conteudo

- RF03 - Visualizar feed.
- RF04 - Publicar post.
- RF05 - Publicar enquete.
- RF06 - Interagir em enquete.
- RF07 - Curtir post.
- RF08 - Comentar post.
- RF09 - Denunciar post.

### Eventos e Moderacao

- RF10 - Visualizar eventos.
- RF11 - Criar evento.
- RF12 - Confirmar presenca em evento.
- RF13 - Analisar denuncias pelo corpo docente.
- RF14 - Registrar historico de atividades do usuario.
- RF15 - Converter atividades em pontuacao.
- RF16 - Deduzir pontuacao do usuario em caso de denuncia procedente.

## 3. Requisitos Nao Funcionais

- RNF01 - O sistema deve ser desenvolvido com arquitetura orientada a objetos.
- RNF02 - A documentacao deve estar consistente com a implementacao.
- RNF03 - O sistema deve possuir persistencia de dados em banco.
- RNF04 - O sistema deve manter rastreabilidade de acoes por meio de log.
- RNF05 - O sistema deve apresentar mensagens claras de validacao e erro.
- RNF06 - O sistema deve registrar apenas acoes autorizadas por usuario autenticado.
- RNF07 - O sistema deve manter consistencia entre cadastro, publicacao e historico.
- RNF08 - O sistema deve ser adequado ao uso previsto em contexto academico.

## 4. Regras de Negocio

- RN01 - O usuario deve possuir e-mail unico no cadastro.
- RN02 - O cadastro so pode ser concluido com todos os campos obrigatorios preenchidos.
- RN03 - A senha deve atender as regras de validacao definidas pelo sistema.
- RN04 - Somente usuarios autenticados podem realizar publicacoes e interacoes.
- RN05 - Apenas o corpo docente pode analisar denuncias.
- RN06 - Toda acao relevante deve gerar log.
- RN07 - A pontuacao deve ser atualizada conforme acoes validas do usuario.
- RN08 - Denuncias procedentes podem reduzir a pontuacao do usuario responsavel.
- RN09 - Eventos devem possuir dados obrigatorios antes de serem publicados.
- RN10 - Posts e enquetes devem ser exibidos no feed apos armazenamento com sucesso.

## 5. Matriz de Relacionamento RN x RF

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

## 6. Referencia Visual

![Modelo conceitual do projeto Meets](imagens/modelo_conceitual.png)